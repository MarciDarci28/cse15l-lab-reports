# Lab #2: Week 4

Howdy! For this lab I worked on creating and fixing bugs in a program! Yay :)

Here are three code changes to our program that we made to fix our buggy test files.

## Code Change #1
![change1](https://user-images.githubusercontent.com/86495731/166407658-20efcf5c-293b-4adb-b1f7-a845b3b5784a.png)

Here is the test file for a failure-inducing input that prompted me to make this change: [Link here!](https://github.com/MarciDarci28/markdown-parser/blob/8d7d89325461c3cb859de64801559f2febb073a7/test-file2.md)

Here is the symptom of that failure-inducing input via the command line output:

![error1](https://user-images.githubusercontent.com/86495731/166408426-5c92d036-12b6-4e93-af69-13d78a9c2537.png)

The output runs an infinite loop, causing a program runtime error and for the program to fail.

In summary, the bug is caused because the test file was missing an open parenthesis for the link. Because it was missing, the program searched constantly for the parenthesis. An infinite loop is created because the while loop condition is never met with the missing parenthesis.



## Code Change #2

![change2](https://user-images.githubusercontent.com/86495731/166407660-35d53a50-004e-4209-8457-677731f5d72d.png)

Here is the test file for a failure-inducing input that prompted me to make this change: [Link here!](https://github.com/MarciDarci28/markdown-parser/blob/8d7d89325461c3cb859de64801559f2febb073a7/test-file3.md)

Here is the symptom of that failure-inducing input via the command line output:

![error2](https://user-images.githubusercontent.com/86495731/166408430-be9e19d5-0ea7-408f-81db-d5d06dad6fd2.png)

The output runs an infinite loop, causing a program runtime error and for the program to fail.

In summary, the bug is caused because the test file was missing an open bracket for the link. Because it was missing, the program searched constantly for the bracket. An infinite loop is created because the while loop condition is never met with the missing bracket.

## Code Change #3

![change3](https://user-images.githubusercontent.com/86495731/166407662-94ed322c-e296-4421-bb78-ac7f402b3c4b.png)

Here is the test file for a failure-inducing input that prompted me to make this change: [Link here!](https://github.com/MarciDarci28/markdown-parser/blob/8d7d89325461c3cb859de64801559f2febb073a7/test-file4.md)

Here is the symptom of that failure-inducing input via the command line output:

![error3](https://user-images.githubusercontent.com/86495731/166408433-51cbb079-d24e-40be-87dd-333f910224cd.png)

The output runs an infinite loop, causing a program runtime error and for the program to fail.

In summary, the bug was caused because of an extra space in the input file. An infinite loop is created because the ending condition for the while loop is not met, since it searches for an input in an empty space that is not there, thereby causing a runtime error.
