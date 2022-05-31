# Week 8: Lab Report 4 -- Kailah Dawson

Howdy.

In this Lab Report, I will be testing 3 snippets of code for both my own markdown-parse repository, and the repository my group reviewed in week 7.

My markdown-parse repository: [MarciDarci28](https://github.com/MarciDarci28/markdown-parser)

The markdown-parse repository I reviewed: [canitry](https://github.com/canitry/markdown-parser)

--------------------------------------------------------------------------------------------------------------

## Snippet 1

#### *Expected Output*

(![snip1](https://user-images.githubusercontent.com/86495731/171090635-5b5c9ce5-2ec9-4909-8082-76485958ec23.png))

This markdown snippet used with `MarkdownParse.java` should produce:
```
['`google.com','google.com','ucsd.edu']
```

#### *Code in `MarkdownParseTest.java`*

```
@Test
public void test_snippet1() throws IOException {
    assertEquals(List.of("`google.com", "google.com", "ucsd.edu")
    ,MarkdownParse.getLinks(Files.readString(Path.of("Snippet1.md"))));
}
```

#### *My `MarkdownParse.java`*

The test failed when it was runned on my markdown-parse. Here is the specific part of the JUnit output that shows the test failure:

```
[cs15lsp22arl@ieng6-202]:markdown-parser:421$ make test
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
JUnit version 4.13.2
........E...
Time: 0.024
There was 1 failure:
1) test_snippet1(MarkdownParseTest)
java.lang.AssertionError: expected:<[`google.com, google.com, ucsd.edu]> but was:<[url.com, `google.com, google.com]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at MarkdownParseTest.test_snippet1(MarkdownParseTest.java:82)

FAILURES!!!
Tests run: 11,  Failures: 1

make: *** [test] Error 1
```

#### *Reviewed from Week 7 `MarkdownParse.java`*

The test failed when it was runned on week 7's markdown-parse. Here is the specific part of the JUnit output that shows the test failure:

```
[cs15lsp22arl@ieng6-202]:markdown-parser:428$ make test
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
JUnit version 4.13.2
...E............
Time: 0.023
There was 1 failure:
1) test_snippet1(MarkdownParseTest)
java.lang.AssertionError: expected:<[`google.com, google.com, ucsd.edu]> but was:<[url.com, `google.com, google.com, ucsd.edu]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at MarkdownParseTest.test_snippet1(MarkdownParseTest.java:95)

FAILURES!!!
Tests run: 15,  Failures: 1

make: *** [test] Error 1
```

#### *Do you think there is a small code change that will make snippet 1 work?*

Yes, it would be possible to make a less-than-10 line code change to cross-check for backticks within the file. This can be done by checking if the backtick is present in the file, and then searching for the closing backtick to get the link between the two. Otherwise, ignore file.

--------------------------------------------------------------------------------------------------------------

## Snippet 2

#### *Expected Output*

![snip2](https://user-images.githubusercontent.com/86495731/171090645-c1b0de0a-380c-4194-9d6d-53632dc92bea.png)

This markdown snippet used with `MarkdownParse.java` should produce:
```
["a.com", "a.com(())", "example.com"]
```

#### *Code in `MarkdownParseTest.java`*

```
@Test
public void test_snippet2() throws IOException {
    assertEquals(List.of("a.com", "a.com(())", "example.com")
    ,MarkdownParse.getLinks(Files.readString(Path.of("Snippet2.md"))));
}
```

#### *My `MarkdownParse.java`*

The test failed when it was runned on my markdown-parse. Here is the specific part of the JUnit output that shows the test failure:

```
[cs15lsp22arl@ieng6-202]:markdown-parser:431$ make test
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
JUnit version 4.13.2
........E...
Time: 0.042
There was 1 failure:
1) test_snippet2(MarkdownParseTest)
java.lang.AssertionError: expected:<[a.com, a.com(()), example.com]> but was:<[a.com((]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at MarkdownParseTest.test_snippet2(MarkdownParseTest.java:88)

FAILURES!!!
Tests run: 11,  Failures: 1

make: *** [test] Error 1
```

#### *Reviewed from Week 7 `MarkdownParse.java`*

The test failed when it was runned on week 7's markdown-parse. Here is the specific part of the JUnit output that shows the test failure:

```
[cs15lsp22arl@ieng6-202]:markdown-parser:436$ make test
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
JUnit version 4.13.2
...E............
Time: 0.029
There was 1 failure:
1) test_snippet2(MarkdownParseTest)
java.lang.AssertionError: expected:<[a.com, a.com(()), example.com]> but was:<[a.com, b.com, a.com(()), example.com]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at MarkdownParseTest.test_snippet2(MarkdownParseTest.java:101)

FAILURES!!!
Tests run: 15,  Failures: 1

make: *** [test] Error 1
```

#### *Do you think there is a small code change that will make snippet 2 work?*

There might be a less-than-10 line code change to make snippet 2 work. The approach I'm thinking of is finding the nested parentheses by creating a stack that keeps track of current open brackets. It may take more then 10 lines though, as you have to consider finding the open parenthesis, pushing to the stack, trying to find a matching closed parenthesis, and finally popping it when found.

--------------------------------------------------------------------------------------------------------------

## Snippet 3

#### *Expected Output*

![snip3](https://user-images.githubusercontent.com/86495731/171090647-abce3290-58c0-4c9f-9077-c59e53d89bec.png)

This markdown snippet used with `MarkdownParse.java` should produce:
```
["https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule"]
```

#### *Code in `MarkdownParseTest.java`*

```
@Test
public void test_snippet3() throws IOException {
    assertEquals(List.of("https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule")
    ,MarkdownParse.getLinks(Files.readString(Path.of("Snippet3.md"))));
}
```

#### *My `MarkdownParse.java`*

The test failed when it was runned on my markdown-parse. Here is the specific part of the JUnit output that shows the test failure:

```
[cs15lsp22arl@ieng6-202]:markdown-parser:421$ make test
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
JUnit version 4.13.2
........E...
Time: 0.024
There was 1 failure:
1) test_snippet3(MarkdownParseTest)
java.lang.AssertionError: expected:<[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]> but was:<[
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
, github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at MarkdownParseTest.test_snippet3(MarkdownParseTest.java:94)

FAILURES!!!
Tests run: 11,  Failures: 1

make: *** [test] Error 1
```

#### *Reviewed from Week 7 `MarkdownParse.java`*

The test failed when it was runned on week 7's markdown-parse. Here is the specific part of the JUnit output that shows the test failure:

```
[cs15lsp22arl@ieng6-202]:markdown-parser:430$ make test
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
JUnit version 4.13.2
...E............
Time: 0.027
There was 1 failure:
1) test_snippet3(MarkdownParseTest)
java.lang.AssertionError: expected:<[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]> but was:<[
https://www.twitter.com
, 
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedu
le
, https://cse.ucsd.edu/
]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at MarkdownParseTest.test_snippet3(MarkdownParseTest.java:107)

FAILURES!!!
Tests run: 15,  Failures: 1

make: *** [test] Error 1
```

#### *Do you think there is a small code change that will make snippet 3 work?*

Yes, it would be possible to make a less-than-10 line code change to make snippet 3 work. One way to approach this would be finding the next matching parenthesis/bracket regardless of its presence within the same line in the file.

