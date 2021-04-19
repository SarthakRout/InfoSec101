# Basics of Vi(Improved) aka *Vim*:

Vim is a completely keyboard-operated text editor, and can be quite efficient to use.
<br/>
Something useful to know in the beginning is that Vim provides different types of "modes"/"views", which are handy for different purposes.<br/>
&emsp; 3 basic modes discussed are: <br/>
&emsp; &emsp; 1) Normal Mode (`Esc`) : This view is used to run editor related commands.<br/>
&emsp; &emsp; 2) Insert Mode (`i..`) : This view is used to edit files.<br/>
&emsp; &emsp; 3) Visual Mode (`v..`) : This view is used to highlight and modify areas of text.<br/>
Each of these views' name would be displayed at the bottom once you enable any of them.<br/>
<br/>
First of all, Type `vim file_name` to open/create and open a new file with this name in Vim.<br/>
<br/>
To quit vi, while in normal mode, type `:wq` which would 'write' and 'quit' the file, while typing `:q` and `:q!` would quit with and without warning.<br/>
<br/>
Now, some basic keys that would help you move around in Vim.<br/>
(Note that highlighted region/line refers to the cursor position)<br/>
<br/>
Insert Mode:	<br/>
&emsp; 1) `i`   - Used to enter insert mode, with the cursor just before the highlighted region.<br/>
&emsp; 2) `a`   - Used to enter insert mode, with the cursor just after the highlighted region.<br/>
&emsp; 3) `o`   - Used to enter insert mode, with the cursor just below the highlighted region's line.<br/>
&emsp; 4) `O`   - Used to enter insert mode, with the cursor on the same line, shifting the highlighted region below.<br/>
&emsp; 5) `$`   - Used to enter insert mode, with the cursor at the end of the highlighted line.<br/>
<br/>
Visual Mode:<br/>
&emsp; 1) `v`   - Used to enter visual mode.<br/>
<br/>
Normal Mode:<br/>
&emsp; 1) `Esc` - Used to enter Normal mode, Commands are given starting with a colon ':' in general.<br/>
&emsp; 2) `yy`  - Used to yank (copy) the highlighted line.<br/>
&emsp; 3) `p`   - Used to put (paste) the copied content after the cursor.<br/>
&emsp; 4) `P`   - Used to put (paste) the copied content before the cursor.<br/>
&emsp; 5) `dd`  - Used to delete the highlighted line.<br/>
&emsp; 6) `u`   - undo the last move.<br/>
<br/>
To get help inside Vim itself, type `:help`.<br/>
<br/>
Bash is a shell scripting language. To create a bash file, create a file with '.sh' extension, start the file with `#!` (shebang) and then the interpreter's location. e.g. `#!/bin/bash`.<br/>
After creating the file, you must change it to an executable file, in order to execute it! (Simple enough)<br/>
You can do this by the command `chmod +x file_name.sh` in the terminal. Execute the file with './file_name.sh'.<br/>
<br/>
You can run bash commands inside vim itself, while in normal mode. Start with ':!' and enter the bash command, or even run bash scripts(files). e.g. `:!./hello.sh` will run this script in the terminal.<br/>
<br/>
Some of the basic bash commands are:<br/>
&emsp; 1) Comments: Start with `#` symbol to comment a line in bash files.<br/>
&emsp; 2) Declaring a variable: <br/>
&emsp; &emsp; &emsp; `a='your content here'` 	#'' are necessary is the argument has spaces. Don't put spaces unneccessarily.<br/>
&emsp; &emsp; &emsp; `echo "double quotes prints $a"`		#"" allow replacement of the placeholders with the value itself.<br/>
&emsp; &emsp; &emsp; `echo 'single quotes prints $a'` 		#'' prints the exact string.<br/>
&emsp; &emsp; &emsp;&emsp; variable type is not mentioned, and every value is considered as a string.<br/>
&emsp; 3) Backticks(\` \`):<br/>
&emsp; &emsp; &emsp; backticks are used to treat strings as commands. e.g. echo \`ls -lah | grep hello\`<br/>
&emsp; 4) 0 is True; 1 is false.<br/>
&emsp; 5) Brackets, Parenthesis and Braces:<br/>
&emsp; &emsp; &emsp; [ ] - is used for logical operations. e.g. [ 3 -lt 5 ] will give 0.<br/>
&emsp; &emsp; &emsp; $( ) - is a command substitution. Similar to backticks. e.g. echo "Infosec folder: $(ls -lah)"<br/>
&emsp; &emsp; &emsp; ${ } - is for scope resolution.<br/>
&emsp; &emsp; &emsp; (( )) - is for arithmetic operations. e.g. `(( $a + $b ))`<br/>
&emsp; 6) `test` command is for testing logical statements.<br/>
&emsp; 7) if-then-fi:<br/>
&emsp; &emsp; &emsp; is a conditional block. Format is like:<br/>
&emsp; &emsp; &emsp; &emsp; if ...<br/>
&emsp; &emsp; &emsp; &emsp; &emsp; then<br/>
&emsp; &emsp; &emsp; &emsp; &emsp; &emsp; ...<br/>
&emsp; &emsp; &emsp; &emsp; fi #denoted the ending of this block.<br/>
<br/>
Note that Bash doesn't throw errors for an undeclared variable. It treats them as undefined.
