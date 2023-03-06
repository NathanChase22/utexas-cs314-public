# Public UT Austin CS 314 Utility Files
Some of my utility files for CS 314 that have been made public with the permission of Mike Scott.

Contributions are appreciated!

## Checkstyle

Checkstyle is a program that will check your code for formatting errors. This includes rules on the [Code Hygiene Guide](https://www.cs.utexas.edu/~scottm/cs314/handouts/hygiene_guide/code_hygiene_guide_framed.html) as well as other stricter rules for more consistent code. Hopefully, this will save you a few points on code styling!

The configuration file is in `cs314.checkstyle.xml`.

### Command Line Usage

You can get the command line version of checkstyle at https://checkstyle.org/.

Once installed, you can run the program with:

```bash
java \
  -jar PATH_TO_CHECKSTYLE/checkstyle.jar \
  -c PATH_TO_CHECKSTYLE_CONFIGURATION/cs314.checkstyle.xml \
  PATH_TO_ASSIGNMENT_FILES/*.java
```

You'll see output like the following:

```
[WARN] /Users/bent/Documents/school/courses/cs314/A1/CodeCampTester.java:481:17: '{' is followed by whitespace. [NoWhitespaceAfter]
[WARN] /Users/bent/Documents/school/courses/cs314/A1/CodeCampTester.java:411:50: '31415' is a magic number. [MagicNumber]
[WARN] /Users/bent/Documents/school/courses/cs314/A1/CodeCampTester.java:26:5: Method main length is 802 lines (max allowed is 25). [MethodLength]
```

If you get warnings in your solution code, fix them! 

In your test file, you can suppress some warnings using the following annotation:

```java
...
@SuppressWarnings({
    "checkstyle:magicnumber",
    "checkstyle:multiplestringliterals",
    "checkstyle:methodlength", 
    "checkstyle:executablestatementcount",
    "checkstyle:descendanttoken",
    "checkstyle:npathcomplexity",
    "checkstyle:javancss",
    "checkstyle:cyclomaticcomplexity"
    // add more if you need to
})
public final class CodeCampTester {
...
```

### Usage with IDE (Instead of Command Line)

This is untested, but there are IDE extensions for [Eclipse](https://checkstyle.org/eclipse-cs/#!/), [IntelliJ](https://plugins.jetbrains.com/plugin/1065-checkstyle-idea), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle), and others (search "\<your favorite IDE\> java checkstyle extension"). Follow the instructions on their respective pages to install and use checkstyle!

# Getting it to work with Eclipse

Okay! So you have CheckStyle installed for your IDE. Now you need to setup the proper configurations, I'm afraid I'm only familar 
with how it works on Eclipse. 

## STEP 0: 
Now before we do anything let's consider if you've sucessful installed the plug in. To do do this go to 
**Preferences > Checkstyle** if you don't see a newly made option for CheckStyle then you must've done the installation wrong. 

## STEP 1: 
Download the XML file provided here, make sure to put it in a directory where you can easily find it for installation. 

## STEP 2: 
click through the **CheckStyle** menu option and there should be a table called ***Global Check Configurations*** 
this is where all of your CheckStyle configurations will appear. Currently you should have *Google Checks* and *Sun Checks* already provided 
to you, however these configurations are not the same as Mike Scott's and I will not recommend using them.

## STEP 3: 
To the right of the configurations table there should be a button labled **New...** click on this. Upon clicking it a window pops up prompting 
you to give a name and type of configuration for your CheckStyle config. I would keep it as a ***Internal Configuration*** and put something like 
'CS314 Checks' 

## STEP 4: 
Now click on the **Import...** button and your computer's file manager should pop up. Take that to the directory of your recently downloaded XML file. 
Click *Ok* and that should be it. 

## STEP 5:
In the table, select your newly created configuration and then in the bottom right corner of the window click *Apply and Close*. That should be it for 
setting up your CheckStyle

# Running On Eclipse 
Now with everything ready, you are given two options on how to run it. Either run CheckStyle on your whole project folder or on one program. I would 
recommend you doing the latter way since it makes it more managable and your 'Problems' window will not be overloaded with errors that aren't even in the 
file you're looking for. 

To run CheckStyle, right click on the program you wish to be check and there should be a **CheckStyle** option appear near the bottom of the list of options, hover your mouse over it and additional commands appear, click on **Check Code with Checkstyle**, this will run the program on your file. 
You will tell it has worked when you see a ton of new Warnings pop up and then your code is highlighted in Yellow. These are your Style errors. 

Sometimes Checkstyle is a little funky with some of the violations, especially with HEADER comments on the top of your code. To remove some violations, 
go to the **Problems** window on your IDE and take your cursor over to the line and the Problems window should take you to that line's violations. 
double click on the single problem, or hold shift and highlight all violations you wish to remove. Then right click and the **Delete** option should be visible. Click on that. 

Finally, if you want to turn off Checkstyle double click on your program in the Project manager and go back to the **CheckStyle** option and click 
**Clear CheckStyle Violations**, this should remove all the violations in that program. 

HOPE YOU ENJOY!
