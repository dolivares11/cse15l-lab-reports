# Week 7 Lab Report 4
## Part 1
### In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base.
'''
'/start <Enter> cebase <Esc> n.n.n. :wq <Enter>
'''
![image](screenshots/lab4pic1.png)
Keys Pressed
'''
/start <Enter>
'''
- /start will highlight the first occurence and once you hit enter it will go to that first occurence in the file.
![image](screenshots/lab4pic2.png)
Keys Pressed
'''
ce
'''
- ce deletes the word and puts the user into insert mode.
![image](screenshots/lab4pic3.png)
Keys Pressed
'''
base
'''
- After being in insert mode, now we type "base" to replace the word we deleted.
![image](screenshots/lab4pic4.png)
Keys Pressed
'''
n.n.n.
'''
- "n" will redo the search and go down to the next instance found. The "." will insert the last inserted text again. Thus, "n.n.n." will change the rest of the instances of start and replace them with "base".
![image](screenshots/lab4pic5.png)
Keys Pressed
'''
:wq <Enter>
'''
- ":wq" and enter will save and exit the file!
## Part 2