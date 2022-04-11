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

Make sure to head on down to the UCSD Account Lookup page [(Look, a link!)](https://sdacs.ucsd.edu/~icc/index.php) to find out what the heck your CSE15L account is called. It should be the characters after "cs15lsp22" (note: this tutorial was made in Spring 2022, so the last 4 characters will vary depending on the quarter).

Here's an example:
![Image](https://user-images.githubusercontent.com/86495731/162650598-3359fa9d-0713-45c1-a08b-8a66d59a7ca5.png)

Once you've got your account name, open a terminal in VScode and connect to the server using the following command prompt:

```
$ ssh cs15lsp22zz@ieng6.ucsd.edu
```
(Note: replace the "zz" with the letters in your course-specific account)

Here's an example of the message you should get after connecting:
![Image](https://user-images.githubusercontent.com/86495731/162651212-458a8c50-67cb-4b5c-82aa-e4c54bf1e417.png)

Process complete! Now your computer terminal on VScode is connected to a computer in the CSE basement! Woohoo! :D

You can now remotely run commands onto the computer server from your local computer, use this power as you wish.

For some extra fun, let's——

## Run Some Commands
Commands are cool. There's a lot of those. Like, a LOT. Too many, one might say.

Here's some essential commands to know:
* cd ~
* ls -lat
* ls -a
* ls </home/linux/ieng6/cs15lsp22/cs15lsp22zz> 

Try running them both on your local computer and on the remote server. Experiment!

For instance, when I used pwd in the terminal while logged into the remote computer, which is a command that prints the full pathname of the current working directory being used, starting from the root directory (which is in this case /home).

![Image](https://user-images.githubusercontent.com/86495731/162652133-73545f7c-8a0c-435c-9ae8-5f4e0f65a45f.png)




