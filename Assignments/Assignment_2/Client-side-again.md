# PicoGym Web Exploitation Writeup

Author: [Keval Moliya](https://github.com/Keval-moliya)

Challenge Page: [Client-side-again](https://jupiter.challenges.picoctf.org/problem/6353/)

## Walkthrough
First I found the source code of the page, there was a javascript in the code which was obfuscated.

Source Code:
```html
<html>
<head>
<title>Secure Login Portal V2.0</title>
</head>
<body background="barbed_wire.jpeg" >
<!-- standard MD5 implementation -->
<script type="text/javascript" src="md5.js"></script>

<script type="text/javascript">
  var _0x5a46=['0a029}','_again_5','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];(function(_0x4bd822,_0x2bd6f7){var _0xb4bdb3=function(_0x1d68f6){while(--_0x1d68f6){_0x4bd822['push'](_0x4bd822['shift']());}};_0xb4bdb3(++_0x2bd6f7);}(_0x5a46,0x1b3));var _0x4b5b=function(_0x2d8f05,_0x4b81bb){_0x2d8f05=_0x2d8f05-0x0;var _0x4d74cb=_0x5a46[_0x2d8f05];return _0x4d74cb;};function verify(){checkpass=document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];split=0x4;if(checkpass[_0x4b5b('0x2')](0x0,split*0x2)==_0x4b5b('0x3')){if(checkpass[_0x4b5b('0x2')](0x7,0x9)=='{n'){if(checkpass[_0x4b5b('0x2')](split*0x2,split*0x2*0x2)==_0x4b5b('0x4')){if(checkpass[_0x4b5b('0x2')](0x3,0x6)=='oCT'){if(checkpass[_0x4b5b('0x2')](split*0x3*0x2,split*0x4*0x2)==_0x4b5b('0x5')){if(checkpass['substring'](0x6,0xb)=='F{not'){if(checkpass[_0x4b5b('0x2')](split*0x2*0x2,split*0x3*0x2)==_0x4b5b('0x6')){if(checkpass[_0x4b5b('0x2')](0xc,0x10)==_0x4b5b('0x7')){alert(_0x4b5b('0x8'));}}}}}}}}else{alert(_0x4b5b('0x9'));}}
</script>
<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:gray">
<div style="text-align:center">
<p>New and Improved Login</p>

<p>Enter valid credentials to proceed</p>
<form action="index.html" method="post">
<input type="password" id="pass" size="8" />
<br/>
<input type="submit" value="verify" onclick="verify(); return false;" />
</form>
</div>
</div>
</body>
</html>
```

So I used this amazing website which also beautifies and deobfuscate javascript (even function calls). Using the website I got the javascript in readable format, it was just checking the input string with the stored string but dividing it in small small sub strings.


Javascript after beautifying and deobfuscating:
```js
function verify() {
    checkpass = document.getElementById('pass').value;
    split = 0x4;
    if (checkpass.substring(0x0, split * 0x2) == 'picoCTF{') {
        if (checkpass.substring(0x7, 0x9) == '{n') {
            if (checkpass.substring(split * 0x2, split * 0x2 * 0x2) == 'not_this') {
                if (checkpass.substring(0x3, 0x6) == 'oCT') {
                    if (checkpass.substring(split * 0x3 * 0x2, split * 0x4 * 0x2) == '0a029}') {
                        if (checkpass.substring(0x6, 0xb) == 'F{not') {
                            if (checkpass.substring(split * 0x2 * 0x2, split * 0x3 * 0x2) == '_again_5') {
                                if (checkpass.substring(0xc, 0x10) == 'this') {
                                    alert('Password Verified');
                                }
                            }
                        }
                    }
                }
            }
        }
    } else {
        alert('Incorrect password');
    }
}
```
From above we have:
```
(0-8) = 'picoCTF{'
(7-9) = '{n'
(8-16) = 'not_this'
(3-6) = 'oCT'
(24-31) = '0a029}'
(6-11) = 'F{not'
(16-24) = '_again_5'
(12-16) = 'this'
```

We can rearrange the above substrings in proper sequence and find out the flag.

## Flag
`picoCTF{not_this_again_50a029}`

## Useful resources (if any)
https://lelinhtinh.github.io/de4js/