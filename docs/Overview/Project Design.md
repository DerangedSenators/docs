# Project Design for our Unity Project

## Use of Repositories
Making use of multiple repositories is a great way to manage sub-projects within the main projects. Reusable components should be managed inside its own repository and then exported as a shared library (`.dll` in Windows and `.so` in Linux). This will effectively make it easier to track changes and show our ability to think ahead as a "startup company" 

In our case, we could split our Game ( The code which directly interacts with Unity) and other components to acheive this

## Semantic Versioning
Semantic Versioning is the process of assinging a unique version number. We will be applying semantic versioning on our releases.
Semantic versioning will work as follows:
`<MAJOR>.<MINOR>.<PATCH>`: The Major shows major changes to the Application which may break external application connections. Minor shows changes which will not break connections and Revision indicates bug fixes.

## Documenting Public APIs
Public APIs expose features of the application/library to external application. These features must hold information so that they can be used correctly. C# Does this in a similar way to Java does with Javadoc albiet it does not generate webpages automatically. (I am looking into that).
C# uses an XML syntax for documentation and you must be familiar with it if you are working with public APIs and it will come in handy for private methods and classes as it will allow team members to understand your code easier. [Reference to C# Documentation Syntax](https://docs.microsoft.com/en-us/dotnet/csharp/codedoc)

