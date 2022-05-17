# Lab Report 3 - Week 6 - Kailah Dawson

--------------------------------------------------------------------------------------------------------------

## Streamlining ssh Configuration

* _Show your .ssh/config file, and how you edited it (with VScode, another program, etc)_

    I used **vim** to edit the config file

![snippet1](https://user-images.githubusercontent.com/86495731/168747350-6db84b26-86c1-44ed-bb71-0df6f1d7b1f0.png)

Here is a screenshot of the vim editor file as well:

![s3](https://user-images.githubusercontent.com/86495731/168747852-eadddcdf-5258-4327-8df1-112bc2d0ba83.png)

* *Show the ssh command logging you into your account using just
the alias you chose.*

    Here is a brief screenshot of me logging into ieng6
    
![s2](https://user-images.githubusercontent.com/86495731/168747671-2751eed1-2b31-4c0d-ad91-6306f2bcd032.png)

* *Show an scp command copying a file to your account using just the alias you chose.*

    This is the scp command I used to copy a homework pdf into my account

![s5](https://user-images.githubusercontent.com/86495731/168748838-c5a28173-ff02-49a1-9219-ae22d8aea994.png)

Here is the file in my directory

![ihl](https://user-images.githubusercontent.com/86495731/168752941-e090e5f5-1533-4b25-9534-4ed70e776c3f.png)

    
--------------------------------------------------------------------------------------------------------------


## Setup Github Access from ieng6

* _Show where the public key you made is stored on Github and in
your user account (screenshot)._

    This is where I have my public key stored on my ieng6 account:
    
![wd2](https://user-images.githubusercontent.com/86495731/168753110-80f94714-b269-4ce5-84e5-7a566e2e867c.png)

And here's the ssh key in my Github

![s8](https://user-images.githubusercontent.com/86495731/168751499-1a3b5e6f-8bf2-4d2c-a942-c01f85f6fd4d.png)

* _Show where the private key you made is stored on your user
account (but not its contents) as a screenshot._
    
    Here is where I have my private key stored on my ieng6 account
    
![las](https://user-images.githubusercontent.com/86495731/168753280-affff9b9-5e92-4a0a-aab2-60ee8fad8bc4.png)

* _Show running `git` commands to commit and push a change to
Github while logged into your ieng6 account._

    Here I cloned the repo on my ieng6 account, added a new file called `newFile.md`, committed the changes, and pushed it to origin from my ieng6 account

![s10](https://user-images.githubusercontent.com/86495731/168759748-dc6053e9-a8ee-4b31-b86c-6978b492871f.png)

* _Show a link for the resulting commit._

Link to commit: [Here](https://github.com/MarciDarci28/markdown-parser/commit/5122d7b7ab4d87452087d436b7e41c3addc8c28e)

--------------------------------------------------------------------------------------------------------------

## Copy whole directories with `scp -r`

* _Show copying your whole markdown-parse directory to your ieng6
account._

    Here I `scp`'ed the markdown-parser directory to our remote machine. Since the hidden git files are copied and the whole directory is quite lengthy, here is a screenshot of only the beginning and end of the copy:

Beginning

![ll2](https://user-images.githubusercontent.com/86495731/168765042-fd4e1ba0-9dfa-4849-9e19-ce64a27708bb.png)

End

![ll3](https://user-images.githubusercontent.com/86495731/168765049-5c3ab8d4-00c6-4c68-b38e-f60574c05d7d.png)

* _Show logging into your ieng6 account after doing this and compiling
and running the tests for your repository._

    Here I ran the tests for my repo using the `Makefile` from lab 6 and `make test` command
    
![aal](https://user-images.githubusercontent.com/86495731/168798940-7d9cd490-5245-406a-8811-d54904e994ce.png)

* _Show (like in the last step of the first lab) combining `scp`, `;`, and
`ssh` to copy the whole directory and run the tests in one line._

    Here I used the following command to copy the `markdown-parser` directory, `ssh`'ed into my remote account and ran the tests:
    
    `scp -r ~/Documents/GitHub/CSE\ 15L/markdown-parser ieng6:~/ ; ssh ieng6 "cd markdown-parser/; make test"`

    Since the screenshots were too long, here is the beginning and end of the program.
    
Beginning

![;las](https://user-images.githubusercontent.com/86495731/168799800-dce1ed33-1cde-4f96-ba79-abd944af7164.png)

End

![lsadk](https://user-images.githubusercontent.com/86495731/168800076-c9e974bc-e03e-4aff-904f-d6dfc24b195a.png)
    
    

    



    
