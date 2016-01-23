# Groovy-Snippets-for-SoapUI
In this repository I'm going to share the clear documentation on Groovy script usage in the context of SoapUI/ SoapUI pro, which would aid the SoapUI users to tackle their day to day web service testing.

## Groovy - Introduction:
Groovy is a dynamic programming language in which most of the program execution processes are done at runtime instead of compile time. 
* Groovy can be categorized into the family of scripting languages. 
* Groovy is a loosely-typed language, which means there is no need to define the data types for the variables and for the return types of the methods. 
* Groovy is a Java friendly language. Being Java friendly means two things: seamless integration with the Java Runtime Environment and having a syntax that is aligned with Java. 

Groovy depends on **Java**. More specifically, executing Groovy files compiled to Java byte code requires the **Java Runtime Environment (JRE)**. Java codes are executable in Groovy platform (ie. GDK: Groovy Development Kit) but, Groovy codes are not executable in Java platform (JDK: Java Development Kit). So Groovy is the super set of Java.

## Getting Started - Basics of Groovy:

### Default Imports:

First thing to be noted is that, Groovy automatically imports the following packages, so there is no need to import these packages explicitly, 

- groovy.lang.* 
- groovy.util.* 
- java.lang.* 
- java.util.* 
- java.net.* 
- java.io.* 
- java.math.BigInteger, java.math.BigDecimal

### Commenting Groovy code:

Single-line comments and multi-line comments are exactly like those in Java, with an additional option for the first line of a script:

Here are some guidelines for writing comments in Groovy:

"//" denotes single-line comments that end with the current line.
 
    // some line comment

Multi line comments are enclosed in "/* … */" markers.

    /*
    some multi line
    
    comment
    */

### Variable and object declaration in Groovy:

The variables can be declared with the keyword def, as shown in the following script:

    def name = "groovy" //declare variable name and assign value soapui

If a variable ids to be declared with specific data type, then it can be given as

    String name ="groovy"

To read the value of a variable, you can just prefix the variable name with $ as in Case 1 or append it as in Java (Case 2).

- Case 1:
    
    def name = "Groovy"
    
    print "Hello $name \n"

- Case 2:

    def name ="Groovy"
    
    print "Hello " +name

### Basics Structures in Groovy:

#### Control Structure:

The syntax of control structures such as "if-else", "for", and "while" are very similar to what we have in other programming languages. Following code snippet uses "if-else” statements

    status = true
    
    strObject = new String("Hello")
    
    myList = ["1","2", "3"]
    
    if (status && strObject && myList) 
    
    { 
    
       //All will evaluate to true
    
       println "Condition is true"
    
    }
    
    else
    
    {
    
       println "Condition is false"
    
    }

Run the code snippet and you will get Condition is true as the output. Here,

*strObject (String object)* and *myList (Collection object)* will return false only if either of the two or both are null or empty.

#### Iterating Structure:

The syntax of the for loop is similar to the following:
    
    for(Object in IterableObject)
    
    {
    
       // Set of Statements.
    
    }




IterableObject is a composite object which has multiple child entries so that it can be iterated. 

    //A List object holding names
    
    def names = ["Saman", "Nethul", "Risith", "Charitha"]//List
    
    for(name in names)
    
    {
    
       //Iterate over the elements in names list
    
       println name
    
    }
