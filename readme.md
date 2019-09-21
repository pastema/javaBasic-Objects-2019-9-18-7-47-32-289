# Overview

This repository is a part of the Java language training plan. Please read the following guidelines before start.

# Getting Start

## Basic Principals

Each repository contains a gradle java project with a number of unit tests. The initial state of all unit tests are *FAILED*. So the aim is to correct the failed test. Please follow the following steps to get the best experience:

* Read the test code and try to understand what it says.
* Trying to fix the test **WITHOUT RUNNING**. This is very important. Because once you run the test, you may find the failure message of the test telling you the expected result. That means you may lose the chance to figure it out by yourself. Note that you should **ONLY** be able to modify code within the **TODO AREA**. The code outside the **TODO AREA** is **NOT** changable.
* Run the test to examine if the fix is correct.
* Answer the following 4 questions after the test is passed.

The 4 questions are:
##Exception Test
1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
	- To understand how the methods work and function.
1. Why the test failed at first?
	- Using the wrong methods and not understanding properly the instruction.
1. Why you corrected the test that way?
	- I followed the methods on where its being thrown and understanding the flow of it.
1. Do you have further questions on this knowledge point?
	- None.

##Inheritance Test
1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
	- To understand the use of classes inheritance.
1. Why the test failed at first?
	- Because I failed to properly understand the required output.
1. Why you corrected the test that way?
	- I followed the flow of the given method and come up with the correct answer.
1. Do you have further questions on this knowledge point?
	- None.


##Object Test
1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
	- To know the use of objects and how to apply it.
1. Why the test failed at first?
	- Because I failed to understand the flow of the method using the objects.
1. Why you corrected the test that way?
	- I studied the flow and understood what it was doing.
1. Do you have further questions on this knowledge point?
	- None.



## Example

Let's take a look at an example:

```java
@Test
void should_pass_by_value() {
  int value = 5;

  tryingToUpdateValue(value);

  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 0;
  // --end-->

  assertEquals(expected, value);
}
```

First, read the test. From the title and code we can know that the test what to examine the behavior when passing an argument. We are not sure what `tryingToUpdateValue` does, so we can jump into its implementation:

```java
private static void tryingToUpdateValue(int value) {
  value += 2;
}
```

Now we have got the full context of the test. The argument is passed by value so the integer will be copied when passing into `tryingToUpdateValue`. Thus the value from the caller site will not change.

Notice that the todo area is in the test method. So we can modify codes within the todo area to pass the test:

```java
  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 5;
  // --end-->
```

Please note that not all todo areas are located in test method. And some todo area may have further restrictions, for example:

```java
  // TODO: You should not write concrete number here. Please find a property or constant instead.
  // <!--start
  final int maximumSymbol = 0;
  final int minimumSymbol = 0;
  // --end-->
```

The hint indicates that we should not write concrete number here. So I should not write `3` or `0xffffffff`, but write symbol (e.g. `Integer.MAX_VALUE`).

## Running Test

You could run unit tests with the help of IntelliJ. But it is also possible to run unit test via command line: `./gradlew build`.

If you just want to build your code without running test. Please use `./gradlew build -x test
`
