# Basic Object Orientated Programming #

Familiarize yourself with .NET suggested coding conventions.  They are found at
*	http://danderson.io/code/c-developer-guidelines/
*	https://www.dofactory.com/reference/csharp-coding-standards
*	https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions  

A quick read is all that is needed. The second link does a good job at explaining why the conventions are a certain way. Abandon the Hungarian coding conventions (like naming integers intNumber) that you saw in tech school. There are several other shop specific conventions that will be introduced to you in the future in a unified document.

Please mark all files with the classification at the top of the file like the following:
```
/*
 * (U) UNCLASSIFIED
 */
```

This only applies to work files.  We do not usually mark automatically generated code like we see code when we work with WinForms.  

Comments also should be done using the XML comments like the following:

/// <summary>
/// (U)
/// </summary>

These comments should be done for class definitions, all class variables, constructors, methods, events, properties, etc.  See the following link for more information about XML comments:
*	https://www.c-sharpcorner.com/UploadFile/1e050f/xml-documentation-in-C-Sharp/
*	https://docs.microsoft.com/en-us/dotnet/csharp/codedoc



## Classes ##

https://www.tutorialsteacher.com/csharp/csharp-class
https://www.tutorialsteacher.com/csharp/csharp-interface
https://www.tutorialspoint.com/csharp/csharp_interfaces.htm

Please read all material prior to the start of this exercise.  Comment all code (Classes, functions, fields, attributes, etc.) as shown in the general programming knowledge section.

Please ensure you are compiling and running the code in debug mode.  See the following links for more information:
•	https://docs.microsoft.com/en-us/visualstudio/debugger/what-is-debugging?view=vs-2019
•	https://docs.microsoft.com/en-us/visualstudio/debugger/debugging-absolute-beginners?view=vs-2019


1.	Create a new console application on .NET Core and name it classes.
2.	Add a new class to the solution.  Use the IDE to rename the class to Circle.
3.	Add the public modifier to the class definition.  Note: Classes are set to the internal by default.  See https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers#
4.	Add one field to the Circle class.  It should use the private access modifier and be type double.  Name it radius.
5.	Next create a default constructor.  Use this to set the radius to zero.  Note:  See the following link for more information about constructors https://www.geeksforgeeks.org/c-sharp-constructors/
6.	Next create a parameterized constructor with one parameter.  The parameter will be a type double and is the radius.
7.	Next create a public function called GetArea that returns a double value.  Use this function to define how to calculate a circle using the radius.  The calculation can be found at the following link https://www.mathsisfun.com/geometry/circle-area.html.
8.	Go to the file Program.cs.  Delete the Console.WriteLine(“Hello World!”); line of code.
9.	Instantiate two instances of the Circle class with one using the default constructor and the other using the parameterized constructor.
10.	Print the areas of both Circle objects to the console window.  Please format the double to only print two decimal places of the double value.
11.	Compile and run.
12.	Notice the Circle instance using the default constructor Area is equal to zero.  There is no way programmatically to change this without changing how changing the Circle class was instantiated.
13.	Go to the circle class.  Add a property with the public access modifier and with a type of double called Radius.
14.	Implement only the set accessor of the Radius property.  Doing this will make this property write-only.  For more information about properties see the following link:  https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/using-properties
15.	Go to the program class.  Add a line of code below the where the default constructor is and change the value of the Circle’s radius of its area using the Radius property.
16.	Compile and run.
17.	You now have the ability to change the change the radius of the circle utilizing properties in the class.

Interfaces


1.	Add a new class to the solution.  Use the IDE to rename the class to IShape.
2.	Change the line that says “class IShape” to “interface IShape”.
3.	Create a declaration for a function called GetArea with a double for the return type.
4.	Go to the Circle class.  Have the circle class inherit from the IShape class.
5.	Go to the program class.  Create an instance of the IShape interface using the Circle class.  Print the area of the new circle that was declared.  Please format the double to only print two decimal places of the double value.
6.	Compile and run.  The new instance of IShape circle shall display the area of the circle.  The IShape interface defines how we will interact with the Circle class and any future class that inherit from IShape.
7.	Find the Circle instance that uses IShape.  On new line type the variable followed by the ‘.’ character.  Notice the Radius property is no longer available.  That is because this instance is of type IShape and not of type Circle.  Delete this line of code.
8.	Add a new class and name it Triangle.
9.	Add the public class modifier to the Triangle class and have the class inherit from IShape.
10.	Compile the application.  An error shall be displayed saying “’Triangle’ does not implement interface.
11.	Add three fields to the triangle class.  All should be of type double.  Name them sideA, sideB, and sideC.
12.	Create an parameterized constructor which will set the three fields above.
13.	Implement the GetArea function to satisfy the IShape interface.  Use the following equation to get the area of the triangle https://www.mathsisfun.com/geometry/herons-formula.html.
14.	Go to the program class.  Create an instance of the IShape interface using the Triangle class.  Print the area of the triangle that was declared.  Please format the double to only print two decimal places of the double value.
15.	Compile and run the application.  The application will display the area of circles and triangles.
16.	Add a new class and name it Rectangle.
17.	Add the public class modifier to the Rectangle class and have the class inherit from IShape.
18.	Add two fields to the rectangle class.  Both should be of type double.  Name them height and width.
19.	Create an parameterized constructor setting the fields above.
20.	Implement the GetArea function to satisfy the IShape interface.  Use the following equation to the area of a rectangle https://www.mathsisfun.com/area.html.
21.	Go to the program class.  Create an instance of the IShape interface using the Rectangle class.  Print the area of the rectangle that was declared.  Please format the double to only print two decimal places of the double value.

Please read the following links before proceeding to the next programming section.
•	https://www.tutorialsteacher.com/csharp/csharp-generics
•	https://www.tutorialsteacher.com/csharp/csharp-generic-collections

Sections 45.10 Sample use of class List<T>, 45.11 Sample use of the Find operations in List<T>, 45.12 Sample use of Sort in List<T> in the following link:  
•	http://people.cs.aau.dk/~normark/oop-csharp/html/notes/collections_themes-list-sect.html


Creating a List of an Interface

Currently as the IShape class is constructed, the IShape interface is compatible with IList<T> collection.

1.	Using the IList<IShape> instantiate a List<IShape> collection.
2.	Add various shapes to the collection using the .Add(IShape shape) method.  Note:  Object initializer syntax can also be used to one or more IShape items in the collection.  See the links before this section for more information.
3.	Create a foreach loop to iterate through each IShape item and print the area.  Format the area to only print 2 digits of the area of the IShape.
4.	Add the following code to your project in the Program.cs file in the Main function:

IList<IShape> shapeList = new List<IShape>();
IShape rectangle = new Rectangle(5, 5);
shapeList.Add(rectangle);
shapeList.Add(new Circle(2));
shapeList.Add(new Triangle(3, 4, 5));
Console.WriteLine(shapeList.Contains(rectangle));
Console.WriteLine(shapeList.Contains(new Circle(2)));
Console.WriteLine(shapeList.Contains(new Triangle(3, 4, 5)));

5.	Compile and run the code above.  The output should be the following:

True
False
False

6.	The issue is the IShape objects don’t implement the IEquatable<T>.Equals method.  What is currently happening the default behavior of Equals is being used.  This only checks the reference identity.  This property will have to be overridden.  See the following link for more information:  https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.contains?view=netcore-3.1
7.	Go to the IShape interface and have the interface inherit from IEquatable<IShape>.
8.	Compile the application.  You should receive three errors in the Circle, Triangle, and Rectangle class for not implementing the Equals method.
9.	Do the following when implementing the ‘bool Equals(IShape other)’ method for the Circle, Triangle, and Rectangle class.  Return false if other is null.  Return true if the instance GetArea() function returns the same value as the other GetArea() function and the if the Object.GetType() method for the instance and other is equal.  See the following link for more information about the Object.GetType() method:  https://docs.microsoft.com/en-us/dotnet/api/system.object.gettype?view=netcore-3.1
10.	Compile and run the code.  The output from step should now be the following:

True
True
True

In the next steps, the IShape interface with the full implementation of a List<T> collection.

1.	Go to the Program.cs file and add the following code to the main function:

List<IShape> shapeList = new List<IShape>();
IShape rectangle = new Rectangle(5, 5);
shapeList.Add(rectangle);
shapeList.Add(new Circle(2));
shapeList.Add(new Triangle(3, 4, 5));

foreach (IShape shape in shapeList)
	Console.WriteLine(“{0}: area: {1:F2}”, shape.GetType(), shape.GetArea());

shapeList.Sort();
foreach (IShape shape in shapeList)
	Console.WriteLine(“{0}: area: {1:F2}”, shape.GetType(), shape.GetArea());

2.	Compile and run.  The program should throw a System.InvalidOperationException with a message stating “Failed to compare two elements in the array.”  This exception occurs because the IShape interface does not implement the IComparable<IShape> interface.
3.	Go to IShape interface and have the interface inherit from IComparable<IShape>.  See the following link for more information:  https://docs.microsoft.com/en-us/dotnet/api/system.icomparable-1.compareto?view=netcore-3.1
4.	Do the following when implementing the ‘int CompareTo(IShape shape)’ method for each class that implements the IShape interface (Circle, Triangle, and Rectangle). Return one if shape is equal to null.  Use the GetArea() function for comparing the instance and other IShape objects.  Note:  Use the CompareTo() function.
5.	Compile and run the application.


Please read the following links before proceeding to the next section:
•	https://www.geeksforgeeks.org/c-sharp-abstract-classes/
•	https://www.w3schools.com/cs/cs_abstract.asp
•	https://www.tutorialsteacher.com/typescript/abstract-class


Refactoring the Shape classes using an Abstract Class

1.	In the last section, there was a lot of redundant code in the Circle, Triangle, and Rectangle classes.  The following code for the Equals method should be in all the classes, or something similar:

public bool Equals(IShape other)
{
	if (other == null) return false;

	return (this.GetArea() == other.GetArea()) && (this.GetType() == other.GetType()); 
}

Additionally, the CompareTo method is the same for the Circle, Triangle, and Rectangle classes.

public int CompareTo(IShape shape)
{
	If (shape == null) return 1;

	return this.GetArea().CompareTo(shape.GetArea());
}

2.	Create a new file called Shape.  Make the Shape class an abstract class and have it inherit from IShape. 
3.	Define a declaration for the GetArea function.  Doing this will implement the IShape interface even though we are using another declaration.
4.	Implement the Equals method in the Shape class.  This will implement the IEquatable<IShape> interface.
5.	Implement the CompareTo method in the Shape class.  This will implement the IComparable<IShape> interface.
6.	Compile the application.  The application should compile.
7.	Do the following for the Circle, Triangle, and Rectangle classes:
a.	Have the classes inherit from the Shape abstract class.
b.	Remove the Equals and CompareTo methods.
c.	Have the GetArea function override the abstract declaration.
8.	Compile and run.  The application’s output shall be identical to the previous section’s output. 
