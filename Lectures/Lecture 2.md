Basics of Vi(Improved) aka *Vim*:

Vim is a completely keyboard-operated text editor, and can be quite efficient to use.

Something useful to know in the beginning is that Vim provides different types of "modes"/"views",
which are handy for different purposes.
	3 basic modes discussed are:
		1) Normal Mode (`Esc`) : This view is used to run editor related commands.
		2) Insert Mode (`i..`) : This view is used to edit files.
		3) Visual Mode (`v..`) : This view is used to highlight and modify areas of text
Each of these views' name would be displayed at the bottom once you enable any of them.

First of all, Type `vim file_name` to open/create and open a new file with this name in Vim.

To quit vi, while in normal mode, type `:wq` which would 'write' and 'quit' the file, while typing `:q` and `:q!` would quit with and without warning.

Now, some basic keys that would help you move around in Vim.
(Note that highlighted region/line refers to the cursor position)

Insert Mode:	
	1) `i`   - Used to enter insert mode, with the cursor just before the highlighted region.
	2) `a`   - Used to enter insert mode, with the cursor just after the highlighted region.
	3) `o`   - Used to enter insert mode, with the cursor just below the highlighted region's line.
	4) `O`   - Used to enter insert mode, with the cursor on the same line, shifting the highlighted region below.
	5) `$`   - Used to enter insert mode, with the cursor at the end of the highlighted line.

Visual Mode:
	1) `v`   - Used to enter visual mode.

Normal Mode:
	1) `Esc` - Used to enter Normal mode, Commands are given starting with a colon ':' in general.
	2) `yy`  - Used to yank (copy) the highlighted line.
	3) `p`   - Used to put (paste) the copied content after the cursor.
	4) `P`   - Used to put (paste) the copied content before the cursor.
	5) `dd`  - Used to delete the highlighted line.
	6) `u`   - undo the last move.

To get help inside Vim itself, type `:help`.

Bash is a shell scripting language. To create a bash file, create a file with '.sh' extension, start the file with `#!` (shebang) and then the interpreter's location. e.g. `#!/bin/bash`.
After creating the file, you must change it to an executable file, in order to execute it! (Simple enough)
You can do this by the command `chmod +x file_name.sh` in the terminal. Execute the file with './file_name.sh'.

You can run bash commands inside vim itself, while in normal mode. Start with ':!' and enter the bash command, or even run bash scripts(files). e.g. `:!./hello.sh` will run this script in the terminal.

Some of the basic bash commands are:
	1) Comments: Start with `#` symbol to comment a line in bash files.
	2) Declaring a variable: 
			`a='your content here'` 	#'' are necessary is the argument has spaces. Don't put spaces unneccessarily.
			`echo "double quotes prints $a"`		#"" allow replacement of the placeholders with the value itself.
			`echo 'single quotes prints $a'` 		#'' prints the exact string.
				variable type is not mentioned, and every value is considered as a string.
	3) Backticks(\` \`):
			backticks are used to treat strings as commands. e.g. echo \`ls -lah | grep hello\`
	4) 0 is True; 1 is false.
	5) Brackets, Parenthesis and Braces:
			[ ] - is used for logical operations. e.g. [ 3 -lt 5 ] will give 0.
		   $( ) - is a command substitution. Similar to backticks. e.g. echo "Infosec folder: $(ls -lah)"
		   ${ } - is for scope resolution.
		  (( )) - is for arithmetic operations. e.g. `(( $a + $b ))`
	6) `test` command is for testing logical statements.
	7) if-then-fi:
			is a conditional block. Format is like:
			`if ...
				then
					...
			fi` #denoted the ending of this block.

Note that Bash doesn't throw errors for an undeclared variable. It treats them as undefined.