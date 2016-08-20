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
git fetch --all
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

To move inside a folder we use the **cd** command

```bash
cd practice
```

Go ahead and try.

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

Display the content of the *inside.txt* file

clue: use the **cat** command

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

We can remove a file using the **rm** command
Go into the practice folder and try to remove the remove.txt file

```bash
rm remove.txt
```

Now verify with **ls** if it's still there.

---
# Extra

Go ahead Play around with rm, trying removing a file that does not exist. what would happen?

---
# Renaming and moving stuff around: mv

We use the **mv** command to move files. in linux, moving and renaming are actually the same.

Lets try renaming the "changeme.txt" file as ```socool.txt```
````bash
mv changeme.txt socool.txt
```
Try **ls** to check what happened!

---

# Who am I? a quick answer for an ancient question: whoami

```bash
whoami
```
Surprise! it echoed your username to the terminal

---

# Extra: basic variables in bash

We can use output from commands in other comamnds. 
One way to do this is using the **$(command_output_here)** syntax

Lets try changing the **socool.txt** file to our username:

```bash
mv socool.txt $(whoami).txt
```

try **ls** to examine the results! woo-hoo!

---

class: center, middle

# Step 3

```bash
cd ~/welcome-cli
git checkout -f step-3
```

Remember: if something gone wrong, you can always reset to this step using the command above

---

# Creating folders: mkdir

inside practice folder we would now create a new folder. named temp
```bash
cd practice && mkdir temp
```

Notice We can chain two commands together with **&&** syntax.

Check what happened in the folder? You just gave life to a new folder

---

# Removing folders: rmdir (well sorta)

Oh. now they want us to remove temp folder. about time. How would we do that?

```bash
rmdir temp
```

You just killed an innocent young folder.

---

# Removing folder: when rmdir isn't enough

* Look there is another folder inside practice. fast! what his name?
* Ok, please remove it.

* OH OH That didn't turn out so well.

* Can you guess why?

---

# Removing folders with content: rm -rf

* Check what remove_me folder contains with **ls** (Always a good idea before deleting)
* You can't remove a folder with content, should be empty.. unless... rm -rf to the rescue

```bash

rm -rf remove_me
```

* mission accomplished

---

# Step 4

## Text fu and pipe

```bash
cd ~/welcome-cli
git checkout -f step-4
```

Remember: if something gone wrong, you can always reset to this step using the command above

---

# Looking at the beginning: head

* It finally happened. Something really bad happened to our app and we don't have a clue.
We need to investigate our app logs. 
* Look at the file system now, take a look at logs/app.log .We'll try to **cat** the file 
* Lots of info.. How can we make since of it? let's start in the beginning.

```bash
head app/logs.txt
```
**head** shows us the beginning of the file. we can specify how many lines do we want

```bash
cat logs/app.log | head -n 5
```

Try it
---

# Intermezzo: The pipe | 

* What just happened here? what is the strange character | in the middle?
* This symbol is called "pipe" and is used to "pipe" data from one unix tool to another. 
* In this example we take the result of  **cat** which is a list of lines and "pipe" it to **head -n 5** 
the head commnad we already know, but specifying we want only the first 5 lines

* We'll see more examples soon

---

# Looking at the end: 

flipping head on the head

```bash
cat logs/app.log | tail -n 5

```

---

# How about in between?

* We need lines 10-15 how do we get them?
* No build in tool for that (I think.. )
* [Unix philosophy](https://en.wikipedia.org/wiki/Unix_philosophy) to the rescue!
    *"Expect the output of every program to become the input to another, as yet unknown, program."*
* how can we combine head and tail to get the lines we need?
 
---
# Combining commands with pipe

```bash

cat logs/app.log | head -n 15 | tail -n 5
```
* So what did we get? lines 10-15
* We pass the result from each stage as an input to the next stage

---

# Step 5

## Redirecting

```bash
cd ~/welcome-cli
git checkout -f step-5
```

Remember: if something gone wrong, you can always reset to this step using the command above

---

# redirecting stream: > and >>

* And now support came back and asked you to send them the logs, but only lines 1-5 they don't care and won't take care
of the problem if you'll send anything else. Just a text file with the relevant lines from the logs.

* How can we do that? we already know how to get the 5 first lines, but how should we write it to a file?

* We need to take the result "stream" from the previous command and write it into a file instead of into our terminal like we did until now.
 in linux we call it "redirecting" 

* And done like this:

```bash

tail logs/app.log -n 5 > email_logs.txt

```

* Now please take a look at the content of email_logs.txt? win!

---
# Redirecting and appending.
 
* THe current redirect command that we are using **>** is overwriting the file everytime we use it.
* Lots of time we need to append to an existing file without overwriting
* For example when the motherf**rs from support sent us this template we must use with a specific encoded header.
* That's when we use **>>**

```bash
tail logs/app.log -n 5 > support_template.txt
```

---

# Step 6

## Text processing

```bash
cd ~/welcome-cli
git checkout -f step-6
```

Remember: if something gone wrong, you can always reset to this step using the command above

---
# Counting with text: wc

* So how many lines does logs/app.log actually has? 

```bash
cat logs/app.log | wc -l
```

* And how many words? (less useful usually.. )

```bash
cat logs/app.log | wc -w
```
---
# We need more data

* So how many errors did we encounter in the logs? how can we know that?
* What kind of errors?
* Is the answer out there somewhere?

---

# Searching for specific text: grep

* we'll use **grep** to search for lines containing certain text: the word error.

```bash
cat logs/app.log | grep error
```

---

# unix philosophy: combining to get the needed data

* We need to pipe the results into something that can count the number of errors.. 
* And we can count with in bash?
* **wc**

```bash
cat logs/app.log | grep error | wc -l

```

* Now we know how many errors we had

---

# Extra : How would we know how many ValueError ?

```bash

cat logs/app.log | grep ValueError | wc -l 
```

* Try what would happen if we do:

```bash
cat logs/app.log | grep valuerrror | wc -l
```
* Can you spot the difference?
* Grep is sensitive to capitalization

---

# More grepping

* We'll only had a "bite" of grep here, it has lots of variations (fgrep, egrep) and lots of options
* man grep

---

# We need more data (remember?)

* So how many errors did we encounter in the logs? how can we know that?
* What kind of errors?
* Is the answer out there somewhere?

---
# Getting organized and unique: sort & uniq

* So we need to get just the **unique** error types. How can we do that?

```bash
cat logs/app.log | grep error | sort | uniq
```

* Without the sort this would be broken, unique only checks for adjacent lines 

---

# More info and further reading

* [command line chapter in django girls tutorial](http://tutorial.djangogirls.org/en/intro_to_command_line/)
* [The command line is your friend - youtube](https://www.youtube.com/watch?v=jvZLWhkzX-8)
* [The shell chapter in linux journey](https://linuxjourney.com/lesson/the-shell)
* [The text-fu chapter in linux journey](https://linuxjourney.com/lesson/stdout-standard-out-redirect)
* [art of the command line - more advanced](https://github.com/jlevy/the-art-of-command-line/blob/master/README.md)

---

class: center, middle

# Open source rocks!
## Thanks for listening!

---
