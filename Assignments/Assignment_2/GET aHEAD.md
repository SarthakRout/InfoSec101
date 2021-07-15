# PicoGym Web Exploitation Writeup

Author: [Kuldeep Singh Chouhan](https://github.com/kuldeep-singh-chouhan)

Challenge Page: [Get aHEAD](http://mercury.picoctf.net:28916/)

## Walkthrough
To gather some information let's see the HTML source code by using 
`curl http://mercury.picoctf.net:28916/`.
HTML source code would look like :
```html
<!doctype html>
<html>
<head>
    <title>Red</title>
    <link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
	<style>body {background-color: red;}</style>
</head>
	<body>
		<div class="container">
			<div class="row">
				<div class="col-md-6">
					<div class="panel panel-primary" style="margin-top:50px">
						<div class="panel-heading">
							<h3 class="panel-title" style="color:red">Red</h3>
						</div>
						<div class="panel-body">
							<form action="index.php" method="GET">
								<input type="submit" value="Choose Red"/>
							</form>
						</div>
					</div>
				</div>
				<div class="col-md-6">
					<div class="panel panel-primary" style="margin-top:50px">
						<div class="panel-heading">
							<h3 class="panel-title" style="color:blue">Blue</h3>
						</div>
						<div class="panel-body">
							<form action="index.php" method="POST">
								<input type="submit" value="Choose Blue"/>
							</form>
						</div>
					</div>
				</div>
			</div>
		</div>
	</body>
</html>
```

Here, we can see `GET` and `POST` request methods. These are requesting data from `index.php`. To check what `GET` is requesting, we can use `HEAD` method. So, let's try running following command 
`curl -I HEAD -i  http://mercury.picoctf.net:28916/index.php`.
The command returns the flag.

## Flag
`picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}`

## Useful resources
Read about the different [HTTP Request Methods](https://www.w3schools.com/tags/ref_httpmethods.asp).
