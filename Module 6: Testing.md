# Test Driven Development #

## Intro to TDD ##

What is TDD? TDD is a strategy in software development to write tests for what you want before you write code for what to occur. As general rules, 
* Write only enough of a unit test to fail
* Write only enough production code to make the failing unit test pass

This seems like an esoteric concept. So before we demonstrate how to do TDD, let us first understand the nature of tests before we delve into TDD itself.

This lesson will be broken into the following sections
* Writing Tests with C#
* C# TDD 
* Mocking in C#

## Writing Tests with C# ##
Before we jump into TDD, it's helpful to understand what testing is first. Testing is the process in which programmers assess whether or not a specific feature is operating correctly or not. Let's do a simple console application first.

1. In Visual Studio, open the project that you created back in Module 2. It should be named `Classes`.
1. On the File Menu, go to Add --> New Project and search for the MSTest Test Project option for .NET Core.
1. Click Next and name the project ClassesTest
