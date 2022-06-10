# Week 10: Lab Report 5 -- Kailah Dawson

Howdy.

In this Lab Report, I will be choosing two tests from the 652 tests provided in Lab 9, compare both, determine the bugs, and provide a solution on how to fix the bugs.

--------------------------------------------------------------------------------------------------------------

### How you found the tests with different results?

So I ran `script.sh` on markdown-parser from week 9, then placed the results into a `week9results.txt` file in order to later compare. Then I ran `script.sh` on my own markdown-parser, again placing the results into a `myresults.txt` file. Once done, I used `vimdiff` to compare the two files.

*Command Used on Vimdiff to Compare Results from Both Markdown-Parsers*

```
vimdiff markdown-parser_week9/week9results.txt markdown-parser/myresults.txt
```

*Vimdiff Output*

![wkwk](https://user-images.githubusercontent.com/86495731/172982784-eaa1459a-0b0b-4ab0-8e93-341cbdf71fdc.png)

From the output generated, I decided to use the following two test-files with different results:

[573.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/573.md)

[201.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md)

--------------------------------------------------------------------------------------------------------------

## Test File 1: 573.md

The first test file that I will be addressing is good ol' `573.md` (what a catchy name!)

### Indicate both actual outputs

*File Output from Both Implementations*
*(Left is markdown-parser from week 9, right is my own markdown-parser)*

![oooo](https://user-images.githubusercontent.com/86495731/172984955-b99b975f-a5cc-43b4-893b-0f24e9a9a283.png)

### Describe which implementation is correct and the expected output

In this test-file, my version of markdown-parser is correct because the output to be expected is:

```[]``` 

as demonstrated by the CommonMark demo site, which outputs the photo:

![foobar](https://user-images.githubusercontent.com/86495731/172989457-5a755078-b14d-4392-95c3-42bf7241d54f.png)

This is because there is an exclamation mark before the link brackets and parenthesis. The inner text in the first outer pair of brackets got another photo link for bar as well. Hence, there is just a photo implementation with no link.

### Describe the bug for the implementation that is not correct

*Bug in the Week 9 Markdown-Parser Code*
*(Highlighted in image for clarification)*

![fjas;lkafsd;lkj](https://user-images.githubusercontent.com/86495731/172990948-41dd76dd-7504-44d8-88c5-2a39d9961c07.png)

The bug in the code is the fact that the week 9 markdown-parser should check if there is an exclamation point before the open bracket after it is done checking if the double brackets are present. 
The solution would be to check if there is an exclamation point before. If so, update current Index to ```closeParen - 1```. Afterwards, continue search starting from index after closeParen for any other link in the file.

--------------------------------------------------------------------------------------------------------------

## Test File 2: 201.md

The second test file that I will be addressing is `201.md` (I wish my file names were this catchy when coding! lol)

### Indicate both actual outputs

*File Output from Both Implementations*
*(Left is markdown-parser from week 9, right is my own markdown-parser)*

![sdfak;j](https://user-images.githubusercontent.com/86495731/172990080-6eb44ccf-f940-48ce-b471-23e016f793b1.png)

### Describe which implementation is correct and the expected output

In this test-file, my version of markdown-parser is correct because the output to be expected is:

```[]``` 

as demonstrated by the CommonMark demo site, which outputs no link:

![fdjfd](https://user-images.githubusercontent.com/86495731/172990243-308ca5a6-ace5-45e8-ad27-af5dea0c62c1.png)

This is because there is text inbetween the link text and the link itself. Since there is text filler, there shouldn't be an outputted link.

### Describe the bug for the implementation that is not correct

*Bug in the the Week 9 Markdown-Parser Code*
*(Highlighted in image for clarification)*

![jfasldkfkdj](https://user-images.githubusercontent.com/86495731/172991018-e9c3622a-4568-4436-a5e2-7b91d054ffbb.png)

The bug in the code is the fact that the week 9 markdown-parser does not check what is in between the link title and the link itself, which it should be doing. The program should not output a link if there is text in between the link title and the link.
The solution would be to add another condition that checks the difference between closeBracket and openParen.
