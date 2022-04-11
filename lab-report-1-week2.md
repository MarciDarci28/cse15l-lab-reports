# How to Log into a Course-Specific Account on ieng6
Howdy peeps! Congrats on being one of the cool kids in CSE 15L. This is a tutorial to get you started on remotely accessing an ieng6 account from your local computer! 

Let's get the basics out of the way:
## Installing VS Code
If you haven't already done so for your other courses, the first step you need to take is downloading and installing the great Visual Studio Code! Wonderful program, 5/5 stars on Yelp. 

Venture towards the Visual Studio Code website [(Here's a handy link!)](https://code.visualstudio.com/) and follow the instructions provided to download the program for your computer's specific operating system. 

Once you've got the program installed, open up a window and it should look something like this (color themes may vary).
![Image](https://user-images.githubusercontent.com/86495731/162649330-da1a589a-2b03-414d-afec-6e5d2de7fbf3.png)

Got it? Great! Next step: 
## Remotely Connecting
So now we're getting to the part where your local computer will remotely connect to a computer in the CSE basement using a course-specific account (which in this case is for CSE15L). 

> For the Windows users out there, here is a quick little step you will need to take before proceeding:

> Please install the OpenSSH program [(Link provided of course!)](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) so that your computer is able to connect to other computers of the SSH account type.

You know what time it is? Checking your course-specific account name time! 

Make sure to head on down to the UCSD Account Lookup page [(Look, a link!)](https://sdacs.ucsd.edu/~icc/index.php) to find out what the heck your CSE15L account is called. It should be the characters after "cs15lsp22" (note: this tutorial was made in Spring 2022, so the last 4 characters will vary depending on the quarter and year).

Here's an example:
![Image](https://user-images.githubusercontent.com/86495731/162650598-3359fa9d-0713-45c1-a08b-8a66d59a7ca5.png)

Once you've got your wonderful account name, open a terminal in VScode and connect to the server using the following command prompt:

```
$ ssh cs15lsp22zz@ieng6.ucsd.edu
```
(Note: replace the "zz" with the letters in your course-specific account)

Here's an example of the message you should get after connecting:
![Image](https://user-images.githubusercontent.com/86495731/162651212-458a8c50-67cb-4b5c-82aa-e4c54bf1e417.png)

Process complete! Now your computer terminal on VScode is connected to a computer in the CSE basement! Woohoo! :D

You can now remotely run commands onto the computer server from your local computer. Use this power as you wish.

For some extra fun, let's——

## Run Some Commands
Commands are cool. There's a lot of those. Like, a LOT. Too many, one might say.

Here's some essential commands to know:
* `cd ~`
* `ls -lat`
* `ls -a`
* `ls </home/linux/ieng6/cs15lsp22/cs15lsp22zz>`

Try running them both on your local computer and on the remote server. Experiment!

For instance, I used `pwd` in the terminal while logged into the remote computer. `pwd` is a command that prints the full pathname of the current working directory being used, starting from the root directory (which is in this case /home):

![Image](https://user-images.githubusercontent.com/86495731/162652133-73545f7c-8a0c-435c-9ae8-5f4e0f65a45f.png)

> IMPORTANT NOTE -- To log out of the remote server in your VScode terminal, user either:
> * `Ctrl-D`
> * `exit`

Okie dokie, let's keep this train moving!

## Moving Files with `scp`
A pivotal aspect to working remotely is copying files back and forth between the local and remote computer. 

"But tutorial, how do I do that on my ieng6 account?" Don't worry dear 15L student, there's a command for that!

`scp` copies a file from your local computer to a remote computer. Note: Always run this command from your local computer, not on ieng6!)

The way it works is:

`scp <file name>.java cs15lsp22zz@ieng6.ucsd.edu:~/`

When you log into the remote computer ieng6 with ssh again, use the command `ls`. You should then see the file you copied in your home directory! 

To demonstrate, when I copied the file WhereAmI.java onto my ieng6 account and ran `ls` on the remote server, I got:

![Image](https://user-images.githubusercontent.com/86495731/162653935-68230e49-4b28-4c4f-9fad-6ce7be49cc0d.png)

After some experimenting I'm sure you notice the tediousness of entering your password over and over every time you log in or run `scp`. It do be frustrating though, and time-consuming. 

I have good news! There's a great solution:

## SSH Keys
SSH keys creates a pair of files called the *public key* and *private key*, that are connected to the particular locations of your local computer and the remote server. They can be used in place of constantly entering a password.

To set this up run the following on your local computer:
`$ ssh-keygen`
`Enter file in which to save the key
(/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa`
`Enter passphrase (empty for no passphrase):`
(Note: Do NOT add a passphrase for this step, just press Enter)

Once done, the result should look something like:
![Image](https://user-images.githubusercontent.com/86495731/162657793-76d7c65a-0616-4670-920c-e52d429cf725.png)
