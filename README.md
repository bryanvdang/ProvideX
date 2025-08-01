# ProvideX

ProvideX also known as pvxPlus and PVX
30-40 yrs old

Meaning of the colors:

- Bright green, are sub routines, Line Labels

- Teal are variables, string variables have a dollar sign at the end

- Yellow: text that is hardcoded

- Red are syntax things

- White are directives/functions

- ! , dark teal is the comment

Variables:
- String variables end in $
- An empty string will be set to ""
- Numeric variables do not end in $
- A numeric value that is not set will be a 0 which is the same as not set
- No need to explicitly declare variables before using them
<img width="456" height="202" alt="image" src="https://github.com/user-attachments/assets/13160605-5732-4484-b114-23b2e9e5c9ce" />

There are no Booleans but you can simulate booleans variables. 
- Integers: 0 for false or 1 for true
- Strings: "Y"/"N" or "T"/"F"

Commands:
- '/' list everything same as typing 'list'
- Display a line $ls + line number
- Renumber the lines $renumber
- Save $save "file path"
- Display directories $?pfx

LS Command:
- Command $ls "line number", b
- Will take you to the line number in the code
- Command to take you to a line label until it reaches a return. 'b' for block. List out the block
$ ls "line label name", b


How to create a program that prints string text and a numeric value
<img width="863" height="530" alt="image" src="https://github.com/user-attachments/assets/5aa62459-cc5c-441e-ba76-fa4f7ff401d5" />

Line Labels:

GOSUB:
- Good to use. Try to use instead of using lines. Using lines doesn't tell you what the code does but at least with line labels you can kind of get an idea of what is happening
- Maintaining the flow of code, "let's do something outside of the current code block", and keeps code clean to section it off.
- Gives you an easy way to end a function early. If you look at line 130, it reads but if there is an error, skip whatever is left (skip 140) and go straight to the return. This logic is usually used for validation. If you get data validate it, if it fails then hit the return.
- <img width="252" height="106" alt="image" src="https://github.com/user-attachments/assets/10126ce4-ab3a-4ab7-836e-bd93233bff28" />

GOTO:
- frowned upon, just jumps around code (Bad practice)
- <img width="494" height="138" alt="image" src="https://github.com/user-attachments/assets/3611480f-3c4f-42c7-b185-d01e759d716c" />
This code is a sub routine, where we localize the variables,
- We set the file
- We're going to open the file we just looked at
- We're going to read from it
- Close it, then print something out.
- Nothing should be bleeding out

If you a subroutine to return something, don't localize the variable.

If you don't use LOCAL, you are expecting it to be set.

When going through files, its better to use for loops and while loops and we commonly use select loops because select loops tie directly into files. A select loop would loop through this file. 

- You can assign variables in the LOCAL variables when its initialized.
- <img width="364" height="55" alt="image" src="https://github.com/user-attachments/assets/f1bda6a6-d52b-4c2c-9702-54356841d8d7" />





