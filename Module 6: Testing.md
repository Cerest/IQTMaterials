# Test Driven Development #

## Intro to TDD ##
What is TDD? TDD is a strategy in software development to write tests for what you want before you write code for what to occur. As general rules, 
* Write only enough of a unit test to fail
* Write only enough production code to make the failing unit test pass

This seems like an esoteric concept. So before we demonstrate how to do TDD, let us first understand the nature of tests before we delve into TDD itself.

This lesson will be broken into the following sections
* Writing Tests with C#
* TDD Methodology
* C# TDD 
* Mocking in C#

## Writing Tests with C# ##
Before we jump into TDD, it's helpful to understand what testing is first. Airmen coming straight from tech school have no experience with unit testing and it's helpful to create an initial impression of what testing can do. Testing is the process in which programmers assess whether or not a specific feature is operating correctly. Let's do a simple console application to help demonstrate this.

1. In Visual Studio, open the project that you created back in Module 2. It should be named `Classes`.
1. After opening that solution, on the File Menu, go to Add --> New Project and search for the MSTest Test Project option for .NET Core.
1. Click Next and name the project ClassesTest. Click Create. You might notice in the solution explorer of Visual Studio that there now exists a new seperate section for ClassesTest. It should have something that appears like a chemistry beaker as an icon.
1. Under ClassesTest in the solution explorer, right click on dependencies and click on "Add Project Reference on the solution explorer.
1. Click on Projects and then select Classes. Let us look at the newly created UnitTest1.cs class file that we just created.

```
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace ClassesTest
{
	[TestClass]
	public class UnitTest1
	{
		[TestMethod]
		public void TestMethod1()
		{
		}
	}
}
```

6. Let us first test whether or not our GetArea function in Triangle.cs is functioning properly. First, we need to add `using Classes;` to the top of our testing class file. This tells Visual Studio to know where to look.
6. Next, let us do some renaming. This step isn't needed but helps us organize our class files once our testing suite grows large in more complicated projects. Firstly, rename the file `UnitTest1.cs` to `TriangleTest.cs`. Then rename TestMethod1 to `GetAreaTest`. This communicates that every test in the TriangleTest Class *probably* has to do with triangles and that GetAreaTest *probably* tests the GetArea method.
6. Instantiate a new triangle inside GetAreaTest(). Name it anything you like. 
    1. Doing `var aCuteTriangle = new Triangle()` doesn't work. Why?
    1. Doing `var aCuteTriangle = new Triangle(3, 4, 5)` could get you the error "Is inaccessible due to its protection level." Why would someone get this error?
    1. Doing `var aCuteTriangle = new Triangle(1, 2, 3)` is also a bad idea. Why?
6. After managing to instantiate a triangle with the dimensions of 3, 4, 5. Calculate the expected area in your head. (I believe in you!).
6. Below your instantiation, type `var expected = x;`, where `x` is whatever your mental math **expect**s.
6. In the next line type `var actual = nameOfTriangle.GetArea();` This is the value your program **actual**ly produced.
6. Now we get into the testing. All testing frameworks use an Assert command. On a new line, type `Assert.` and look through the tool tips. Did you find a command to see whether or not wo values were equal?
6. Your GetAreaTest should now look like the following,
```
[TestMethod]
public void GetAreaTest()
{
	var nameOfTriangle = new Triangle(3,4,5);
	int expected = QWUICKMAFS;
	double actual = nameOfTriangle.GetArea();
	Assert.FINDTHECORRECTCOMMAND(expected, actual);
}
 ```
6. Don't forget to **comment!** To run this. On the top bar, go to Tests --> Run All Tests. And hopefully there should be green checkboxes.
6. Write a test that verifies that the area of a circle with radius `2/sqrt(pi)` is what you think it is to verify that your implementation of GetArea for Circle is correct.
6. Given this, why do you think testing like this is useful? We can automate these testing procedures to run every time someone tries to edit our code. This helps to make sure that the random changes people make don't mess up existing functions/behaviours.
6. We are not done. NONE of his was TDD. This was just simply demonstrating how to do the most basic of tests. Let us now move onto the basic flow of TDD.

## TDD Methodology ##
To save time, please read this article, https://medium.com/javascript-scene/tdd-changed-my-life-5af0ce099f80. 
