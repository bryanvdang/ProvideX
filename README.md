# ProvideX

ProvideX also known as pvxPlus and PVX
30-40 yrs old
---
Meaning of the colors:

- Bright green, are sub routines, Line Labels

- Teal are variables, string variables have a dollar sign at the end

- Yellow: text that is hardcoded

- Red are syntax things

- White are directives/functions

- ! , dark teal is the comment
---
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
- 
---
Line Labels and Subroutines:

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

---
LOCAL Statements:
If you don't use LOCAL, you are expecting it to be set.

When going through files, its better to use for loops and while loops and we commonly use select loops because select loops tie directly into files. A select loop would loop through this file. 

You can assign variables in the LOCAL variables when its initialized.
- <img width="243" height="37" alt="image" src="https://github.com/user-attachments/assets/118bdaeb-554a-44f0-bac1-984e34a3dc4a" />

- LOCAL statements can protect values from being changed while in a GOSUB or PERFORM
- LOCAL name$
This will keep the variable of name$ to its current state, but once the block has finished, it will reset the value to its original state.
---
PERFORMS are exactly the same as a subsroutine aka gosub but Performs are in a different program
<img width="180" height="17" alt="image" src="https://github.com/user-attachments/assets/bc4be501-7d98-4379-a5b2-59c44b89a447" />
- Similar to a GOSUB but in a different program
- The quotes need the program name followed by the gosub. It has to be a gosub and not a line number
- Perform will stop at a return but if there's a GOTO, the GOTO will bypass the return until its done running the code in the GOTO. Then it will return to the stack it was at before.

---
CALLS are like performs but will localize everything that's not passed into it.
- Similar to a perform but has parameters
- Allows for default values
- They are more similar to a function
- You only have to be explicit in parameters. If you're passing in a string, you have to make sure the accepting parameters is set to a string as well
- Calls require 'exit' to get out of the program while subroutines and performs require returns
- Adding parenthese is a way to prevent the variable from being changed.
- <img width="307" height="14" alt="image" src="https://github.com/user-attachments/assets/ab61f3da-82ca-4516-b751-6ab9331c8001" />
-Good because they help you containerize code, that can be globally used across the system, protects variables so you don't have to create a long list of localization.
-Downside side is it gets difficult when it involves multiple file channels.


<img width="291" height="85" alt="image" src="https://github.com/user-attachments/assets/b5067104-0d9b-4ee2-9d7b-bf6015d06841" />
Be sure to put an 'END' at the end of the GOSUB(s)

Use Line labels when using GOSUBs so you don't lose your line number and its cleaner.
<img width="746" height="419" alt="image" src="https://github.com/user-attachments/assets/ae54d077-ae44-4f16-80c0-dbd0b9e2c01e" />

---
Functions:
- Cvs (similar to stp, stripping spaces, manipulating the contents of the spacing the string you pass in). CVS is more of a binary function. You send it parameter 1, which is strip deleting, parameter 2 is strip the trailing, parameter 3 is strip deleting.
    - Lets you utilize control characters, so if a third party has junk on a string you don't want, you can convert it to spaces.
- Stp (stp is the basic version, you're stripping the front, the back, you can even strip certain characters out of the string.
    -<img width="247" height="343" alt="image" src="https://github.com/user-attachments/assets/6cc0186a-4ac1-4889-bc6f-3fcaa5f21d4b" />
- Pad
    - Padding, checking to see if a value is a certain length
- Tbl
    - Table statement, similar to a ternary. In a table function, you can have multiple results. The first parameter in your table statement, is the numeric value of what you want to happen.
In this example is, the string we give it is "W". It will iterate over the string "DWM". First case, if it can't find anything it will return "???", if the string was D it would return Daily, W Weekly, or M monthly. In our example we have W so it returns weekly
    - <img width="245" height="47" alt="image" src="https://github.com/user-attachments/assets/857c7741-b969-4dfa-8810-09c877d438b7" />
    - In this example should print "one" since its in the Oneth position, if x was 4, it would error stating it doesn't exist within the range (#41)
    - <img width="374" height="128" alt="image" src="https://github.com/user-attachments/assets/2c70b12e-70d4-46b2-9c59-9d793ea16ff9" />
    - Char replacement must have matching length
        - <img width="483" height="153" alt="image" src="https://github.com/user-attachments/assets/ea264892-951d-4f30-9ce3-1e1ad985904a" />
- Cse
    - Case statement within a function instead of a switch case
- Not
    - Will take the not of the value
- Nul
    - Tell you if it’s a null or not (if its empty)
    - A value with 6 spaces is also null
    - Use to check if something is actually being set

- Num
    - Taking the number of something
    - <img width="353" height="241" alt="image" src="https://github.com/user-attachments/assets/9c1cf1d5-3584-4c73-9a9e-feed4cc974c8" />
- Pos
    -What's the position of this value compared to this other value and will return a numeric value
- Sub
    - Substitute text. Replace certain characters within this string. Change the 'e's to 'o's. Something of that nature
- Ucs
    - Upper case. Also a lcs for lower case
- Str
    - Will see a lot. Practically take the string value of this number
	- Has lots of formatting masks. Use for currency or decimal
- Int
    - Not used too much but it takes the integer of a number<img width="583" height="257" alt="image" src="https://github.com/user-attachments/assets/7f4b50ff-1305-4ad5-93a3-dcaec5f67faa" />
- Mid
	- Can be used to take off the first char of a string
 	- mid(string$, 2)
More Functions:
- Sys(): 
	- Basically sends out a command to the server to say, go process this.
 - 



---
Arithmetic:
- <>, = 	not equals to	Not equal to, equal to
- +,-,*,/ 	Add, Minus, Multiply, Divide
- ++,--		Increment, Decrement
- <, >		Less than, greater than

---
Select Loop:

- This example (line 90) is saying, go select, grab these values, from this file channel, we're going to force it to start at the beginning and then we're going to keep going until we hit the end $FF$ because we don't usually store hex values in your key structure but $FF$ is a way to force it to the end. This will print values 1 through 30.
	- <img width="423" height="189" alt="image" src="https://github.com/user-attachments/assets/5ed9bf56-a7a1-4675-b879-5bd722360f37" />
- Another way to show a specific range. The begin and end is based off the key structure on line 60.
	- <img width="767" height="584" alt="image" src="https://github.com/user-attachments/assets/4dc3bd22-6eb4-4b46-8919-858429d4ea55" />
- You can also add a WHERE clause, in this example we're looking at the value not the padded key value
	- <img width="935" height="89" alt="image" src="https://github.com/user-attachments/assets/655b9fd1-a865-443b-908d-be96ebe05ac6" />
- Generally speaking, when we're selecting this value (COUNT$), this is dealing with what's called an I.O list. Meaning this is a hard-coded list of variables that I'm dealing with, which is okay to deal with when dealing with serial files and memory files but when we're dealing with providex files, we don't want to do I.O lists because they change occasionally, and then you have to update all the code that reference those to have the updated version of the I.O list. 
	- <img width="918" height="29" alt="image" src="https://github.com/user-attachments/assets/8766436c-0316-41d2-b515-448841278141" />
- This code is saying: we're going to write 3 fields to our memory file
A way to print from our mem
- <img width="557" height="90" alt="image" src="https://github.com/user-attachments/assets/b2eef291-cd05-4f32-9ace-57e45a40740d" />

- How to do a select from an embedded I/O list
	- <img width="570" height="50" alt="image" src="https://github.com/user-attachments/assets/ef0d25d6-ef3d-40f7-8f36-f7be3bee6796" />

---
If - Else:
- <img width="352" height="65" alt="image" src="https://github.com/user-attachments/assets/cea0d6a4-e6a4-40eb-91b4-6a030d4becaa" />
END_IF is practically a new line. No matter what happens, x will be equal to 6.
- Don't use brackets when using if else because we can't indent
- If it’s a case where you need to use brackets to readability, use GOSUB.

In this example we're, this should return success the value 3 exists in the table. If the value was 4, we would hit the error message, string$ would not be set and the message would be set to "Failed". Which would be returned on line 30.

<img width="732" height="326" alt="image" src="https://github.com/user-attachments/assets/d3e3b3a3-89b7-4710-a59c-9c16a36d742d" />
---

While Loop:
- Traditionally speaking, there isn't a lot of while loops that are use. However, the one while loop that is used a lot is a while true or while 1.
- A loop that goes on infinitely, nothing's going to stop it until we come up with a value to stop it.
- While condition will check at the end of the condition (it won't check mid code)
- Needs to have 'WEND' to know where to end
- <img width="1532" height="818" alt="image" src="https://github.com/user-attachments/assets/e3957fb2-186e-4d56-be0a-02881ef1cfa2" />
- <img width="1014" height="600" alt="image" src="https://github.com/user-attachments/assets/5c5cdaa9-e8e3-4b16-8cc6-1b20ea605274" />

Example 2:
- <img width="339" height="137" alt="image" src="https://github.com/user-attachments/assets/a85a45fc-5e0d-4af3-a6e6-71e0b6a63765" />

---

Switch Statement:
- Needs a break statement. If there is no break, it will bleed into the next statement until it finds a break
- Needs a default
- <img width="463" height="189" alt="image" src="https://github.com/user-attachments/assets/1ff645ac-7a33-41bf-abc0-7cef66cf94b8" />

---
For-Loop:
- For-I loop, follows the following convention
- <img width="194" height="87" alt="image" src="https://github.com/user-attachments/assets/be18b159-2fb6-4a6f-940c-d30b2d972bd8" />
- <img width="263" height="474" alt="image" src="https://github.com/user-attachments/assets/210c20c8-531b-47f8-b2d6-d932d2606298" />

To display every other:
- <img width="338" height="24" alt="image" src="https://github.com/user-attachments/assets/e30fffcf-af27-4caa-821b-5ddfbee2a724" />
- <img width="60" height="137" alt="image" src="https://github.com/user-attachments/assets/e68c434f-5032-44ef-8991-fa2ec0eaea72" />

We'll often see for loop for the length of a variable to figure something out.

For-From
- Better than the For-I loop when dealing with this string data
- In this example we're going to store each of these values into the PRC$ that we're iterating from. But for our separator, we're going to use the very last character that is used on the string
	- <img width="491" height="420" alt="image" src="https://github.com/user-attachments/assets/fd069467-102c-4ff1-bcc0-58db8461c669" />
- If you have a bad separator, you will have bad results
	- In this case it thinks the 'D' is the separator
 	- <img width="492" height="110" alt="image" src="https://github.com/user-attachments/assets/a080d9e8-6469-434d-8e7d-79c622eff675" />
---

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
<img width="463" height="230" alt="image" src="https://github.com/user-attachments/assets/5aa62459-cc5c-441e-ba76-fa4f7ff401d5" />

Renumber Command:
- $renumber
- Renumber the lines
- Always save your program before renumbering, if it screws up your code, reload it and fix it (not a big deal)

- How to move a block of code
	- Start at the 20000 block, do it by 10s, starting line, ending line
 	- <img width="420" height="450" alt="image" src="https://github.com/user-attachments/assets/afa05810-f988-45b0-89c0-3d9ee85d1061" />

PGN:
- What is the current program I am in
- $?pgn
- <img width="186" height="47" alt="image" src="https://github.com/user-attachments/assets/af7c85e4-118b-4654-9fc2-80686d1a4c64" />

Move Line: 
- Mv "line you want to move" "line where you want to move it to"

Swap Lines:
- Swap two lines of code
- $swap "line number 1" "line number 2"
- <img width="109" height="13" alt="image" src="https://github.com/user-attachments/assets/56b27660-9ea8-4e75-8b21-cf2f579ecf3f" />


Escape:
- End the program and puts you into debug mode
- Good for debugging after a process takes place

Clip Command: 
- Clip:
- If you type the command $clip, the cursor is gone and now in clip board mode and it wants you to highlight something.  Therefore, highlight something, then click 'enter'. The highlight is then stored into the clipboard
	- <img width="488" height="113" alt="image" src="https://github.com/user-attachments/assets/c0f974a2-9aca-4892-a7c6-dd34bf04a755" />
 	- <img width="653" height="69" alt="image" src="https://github.com/user-attachments/assets/569ec80e-7792-46f4-b739-d768e40421cd" />

Clip/Paste
- You can also clip individual lines if you do $clip + Line number
- A way to copy and paste into other programs or into notepad or chatGPT
- <img width="461" height="303" alt="image" src="https://github.com/user-attachments/assets/bcc1ffcd-c2df-4d4e-a6bc-81b06846e3ef" />

- $Paste2 meaning I want to put it somewhere else.
	- In this example he clipping this code and pasting it at line 10300
 	- <img width="231" height="50" alt="image" src="https://github.com/user-attachments/assets/a8ada0f8-a4cd-4637-9d35-08ae0b643617" />
- $Paste will keep the line number that’s already associated with it. If you're copying from one program to another program. If you want a different line number then use paste2 + Line number
- When pasting, you'll notice 2 additional dashes. It disables the renumbering functionality to avoid preserving it and having it conflict with other matching line numbers. Therefore the system is just trying to be safe but you can simply remove the dashes after pasting
	- <img width="455" height="189" alt="image" src="https://github.com/user-attachments/assets/9217c8c2-1b35-4cce-bae3-49085c1c09c3" />

Join Command:
- Combine two line numbers
	- <img width="1392" height="161" alt="image" src="https://github.com/user-attachments/assets/d03d5c68-1fd5-4d83-884e-15c8a78d4e50" />

Find Command: (Home Built)
- After loading a program, typing $f + variable will highlight matching searches

- If you only care about a variable within this subroutine run command $f -ls "variable name"
	- This command is saying go look at my most recent LS command, and only return matches within that block

Search and replace
- Look through these lines, search for this value and make it equal to this new value

Vars command:
- Vars + "variable name" will show the lines of code that matches the variable name
	- List the lines of code that match this specific variable
 	- <img width="384" height="90" alt="image" src="https://github.com/user-attachments/assets/0d6b07f2-275c-4a60-a920-087fff5e0ced" />
  	- Really comes in handy if you're dealing with numeric vs strings or you're just looking for the numeric version

Delete:
- Code to remove a block, Delete command followed by starting line then ending line
- <img width="236" height="24" alt="image" src="https://github.com/user-attachments/assets/ab45ce04-b0b8-4903-b915-150c05232558" />
- Will remove this block of code
- <img width="446" height="308" alt="image" src="https://github.com/user-attachments/assets/76851f33-38e2-4ab1-b362-bb8bc7b513cf" />

LS Command:
- Command $ls "line number", b
	- Will take you to the line number in the code
- Command to take you to a line label until it reaches a return. 'b' for block. List out the block
	- $ ls "line label name", b
- How to list out a section of code
	- <img width="211" height="117" alt="image" src="https://github.com/user-attachments/assets/d2950583-d4e5-4dea-a1ea-1eeecc3d0a00" />
- $ls 10100, 2b
	- Will give you 2 blocks of code
- List out code will save in memory the last couple lists we've done
	- <img width="597" height="15" alt="image" src="https://github.com/user-attachments/assets/e38e0966-d792-42d3-b861-3a9fcaea1f28" />
	-  If we type $LS2, it would bring us to that block.
 - If you type $LS, it will display the last one that you did.
 - $LS +"Subroutine", it will add the subroutine to our view (Adding to the view)
 	- Its a good way to create a view of stack tracing a problem in the code

Create Block Command:
- $CB
- Creates a block
- Command will ask for line number followed by name of block
- <img width="336" height="64" alt="image" src="https://github.com/user-attachments/assets/913ac9ac-dd97-418f-8edb-bc2c1c279d0c" />
- On enter it will create the block with a Field Line.
- <img width="210" height="94" alt="image" src="https://github.com/user-attachments/assets/e83cc197-310a-4f8f-bfa1-d59384d9c85f" />
- The ^100, 10 is auto generated. It is a special comment that tells the program of how to renumber itself and where it should be.
	- If we did a renumber it would start on a line in the next 100 increment and default by 10s. System default is 10 but you can re command it to use a different default.
 	- So if you're on line 5110, it would put you at 5200.
  	- <img width="220" height="18" alt="image" src="https://github.com/user-attachments/assets/b3c2a4cc-b423-4082-9297-ed1f6fe9fe05" />

- This command sets your END: statement to always be at line 5000
	- <img width="163" height="21" alt="image" src="https://github.com/user-attachments/assets/cac50a0f-f549-463b-b136-b5f25d6a48bd" />

 Command to get back to the main blue menu. The 2 commands do the same thing.
- $run "AIDS"
- $run "SELCT3"

Clip_board Command:
It's very slow to write out to excel. This command clip_board write allows you to copy and paste values and paste to excel in case you ever need to get data/information out to a user, they usually like it in excel. Kind of like a one off thing.
- <img width="155" height="14" alt="image" src="https://github.com/user-attachments/assets/aed4ebde-2d5c-4987-8d80-27e7afcbcce2" />
- Paste in Excel

If you want rows or columns in excel, tab is hex09. 
In this example they would be tab-separated, the last column got a hexD0A to specify that we're on a new row now.
- <img width="346" height="12" alt="image" src="https://github.com/user-attachments/assets/9555a0b0-981e-4a02-a816-7e456f55f9ef" />

Execute command:
Basically dynamically creating lines of code.

Useful commands for troubleshooting:
$dumpscan "value"
	- A memory dump of all the values that are out there that have that value in there. 
$localdump 
	- Similar to dumpscan. It's basically looking at your current environment. You know when you go through a call, it kind of separates the environment because it localizes all the variables? A dumpscan will look at variables that are beyond calls. Where a localdump says to give me everything that is currently available, that is currently set.

$PI command
- Progress indicator. Some utility programs will have this
- Running PI + "line number" is automatically going to create this line of code.
	- <img width="621" height="63" alt="image" src="https://github.com/user-attachments/assets/b7afd67f-e0e3-426b-96b4-56ddb68d73c0" />
- When you run the code, it will run a progress indicator
	- <img width="307" height="21" alt="image" src="https://github.com/user-attachments/assets/110f0a6e-7f64-40a7-981e-59c0e4195918" />
- If you do a F1 while the progress indicator is running, it allows me to escape out of my loops. So if you ever get to the point where you're in an endless loop or I would like to be able to stop my loop from processing. Use a PI, throw an escape in there, and it'll be looking for an F1. When the code get to the 'OBTAIN' it'll check if you hit an F1 and then escape out. Good safety net when you're writing loops, importing data and such.

$VP command:
- Basically view, perform. So if we do VP "Line number", translates to "go show me what this block of code is doing."

- Works with GOSUB, so you can pass in the GOSUB and it'll show it to you.
	- <img width="122" height="116" alt="image" src="https://github.com/user-attachments/assets/6af2c1c0-2a11-49da-b1d4-0d6913e94307" />
- So if you see a PERFORM, do the VP and the VP will show it to you without you having to load up a different program

$Stack command:
- Basically shows where you are in your program. It'll have stack line numbers when you bounce between performs and calls.

Precision:
- By default, MERP usually runs on precision of 5. Sets the precision if precision has changed. If you do precision of -1, it sets everything to a floating point. 
- Caution: if you convert a number to a string, while floating point is active, you will get the scientific notation for that.
	- <img width="79" height="179" alt="image" src="https://github.com/user-attachments/assets/12bf993d-914c-4e7f-895a-88952e4e37dc" />

PRC function:
- Basically says, go set this single value to precision of whatever want, one of the parameters on there. 

Execute Command:

There's been an issue where some data is out of sync between two systems and we need a quick way to resync those. ITNs. So Chris created a program that non provideX users can use. The program would get a list of ITNs that have problems. Line 20 reads in from the clip board putting it in a list.
- <img width="233" height="21" alt="image" src="https://github.com/user-attachments/assets/26ea82e6-8329-42be-b0f4-ff6c794b691d" />

TMUX command: 
- Basically it's going to start this process on the server. We're going to call it this thing (first red line), we're going to go run this program (2nd red line) and here are my arguments to it (next 2 red lines)

WDX command:

The WDX command allows the windX process to connect with our PC as well as save to it. 
E.g. we created a text file with the contents "HELLO WORLD" inside of it.
- <img width="333" height="48" alt="image" src="https://github.com/user-attachments/assets/41ccc652-9c95-4640-9667-164eb5b38c37" />

How to save to users local machine
<img width="1263" height="436" alt="image" src="https://github.com/user-attachments/assets/0427544a-8996-48aa-b79c-37415a025d6d" />

FI command:
- $fi
- Go look up information

PIOL command:
- Print IO list
- print the contents of a IO list or record

Gui command
- $gui
- Only downfall of gui is that you usually only use it to view a file or update a file
- When you need to change a value in the file itself, sometimes it better to update in the gui rather than writing a program to read in the record, change the value, then write it out.

---
Arrays
- In this base array, we're creating a string array with 10 elements
	- DIM meaning dimension
 	- <img width="112" height="13" alt="image" src="https://github.com/user-attachments/assets/cf6c7d46-cb0c-48ee-801b-f148252ca967" />
- Basic arrays are 0 based, meaning they start at 0
	- If you wanted, you could set the base to 1, not sure why, but you could
 	- <img width="133" height="16" alt="image" src="https://github.com/user-attachments/assets/826deabf-cb65-4e29-8e64-45715b091299" />

DIM
- We have directives for DIM and functions for DIM (Dimensionalize)
	- DIM function is to find out information about an array 'DIM()'




















 










 

















































