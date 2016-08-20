class: center, middle

# Welcome to the CLI

###A gentle introduction and Some real live examples

[live presentation](https://alonisser.github.io/welcome-cli) <br/>
[twitter](alonisser@twitter.com), [medium](https://medium.com/@alonisser/), 
[Sad FrontEnd IL](http://sadfrontendil.tumblr.com/)
#####you can also read my political blog: [דגל אדום](degeladom@wordpress.com)
---

# Starting

fork this repo to your github profile (lets say Tara)

Enter to the terminal and

```bash

git clone git@github.com:Tara/welcome-cli.git
cd welcome-cli
git fetch --tags
git checkout -f step-0

```
---

# What is the CLI

Many names:

* The command line
* Bash
* The shell
* The scary black screen

"A text interface to the operating system."

---

class: center, middle

# Step 1

```bash
git checkout -f step-1
```

Remember: if something gone wrong, you can always reset to this step using the command above

---

# Just speaking my mind: echo

```bash
Echo "Hello world"
```

What did you get?

Looks pretty harmless
---
# Looking inside a text file: cat

```bash
cat hello.txt
```

What did you get?

---
# Navigating in folders: cd

To move inside a folder we use the ```cd``` command

```bash
cd practice
```

Go ahead and try

---

# Looking around: ls

But what is there in this new and exciting folder?
We can use the ls command to look around and see what we got here:
 
 ```bash
ls
``` 

Type the ls command: what did you get?

---

# practice for step 1

Display the content of the inside.txt file

clue: use the ```cat``` command

---

class: center, middle
# Step 2

```bash
cd ~/welcome-cli
git checkout -f step-2
```

Remember: if something gone wrong, you can always reset to this step using the command above

---

# Removing stuff: rm

We can remove a file using the ```rm``` command
Go into the practice folder and try to remove the remove.txt file

```bash
rm remove.txt
```

Now verify with ```ls``` if it's still there.

---
# Extra

Go ahead Play around with rm, trying removing a file that does not exist. what would happen?

---
# Renaming and moving stuff around: mv

We use the ```mv``` command to move files. in linux, moving and renaming are actually the same.

Lets try renaming the "changeme.txt" file as ```socool.txt```
````bash
mv changeme.txt socool.txt
```
Try ```ls``` to check what happened!
---
# Who am I? a quick answer for an ancient question: whoami

```bash
whoami
```
Surprise! it echoed your username to the terminal

---
# Extra: basic variables in bash

We can use output from commands in other comamnds. 
One way to do this is using the ```$(command_output_here)``` syntax

Lets try changing the ```socool.txt``` file to our username:

```basg
mv socool.txt $(whoami).txt
```

try ```ls``` to examine the results! woo-hoo!

---


# More info
* [command line chapter in django girls tutorial](http://tutorial.djangogirls.org/en/intro_to_command_line/)
* [The command line is your friend - youtube](https://www.youtube.com/watch?v=jvZLWhkzX-8)
* [The shell](https://linuxjourney.com/lesson/the-shell)

---

class: center, middle

#Open source rocks!

---

class: center, middle

#Thanks for listening!

---
