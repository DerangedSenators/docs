# C# Source Design
Before you begin writing code in C# please take a moment to read this document as It contains the conventions that we, as a group will use throught C# classes.

## C# Naming Conventions
[Please take a look at this page for C# naming conventions](https://github.com/ktaranov/naming-convention/blob/master/C%23%20Coding%20Standards%20and%20Naming%20Conventions.md)

## Our namespace
To the java package, we have namespaces in C#. This will take the form of our reverse domain all in lower case with consecutive words concatenated together: ```me.derangedsenators.<product>.<feature>.<subnamespace>``` more on namespaces [here](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/names-of-namespaces)

## Code file structure
A source file consists of, in order:

1. License or copyright information, if present
2. Import Statements
3. Namespace declaration
4. Exactly one top-level class
5. Exactly one blank line seperating each section that is present

## Non-ASCII characters
For non-ASCII characters, an actual Unicode or equivalent Unicode escape is used. The choice depends only on what makes the code easier to understand, although Unicode escapes outside string literals and comments are strongly discouraged.
For Example:
| Code | Comment |
| ------------- |-------------|
| `string UnitAbbrev = "μs"` |	Best: perfectly clear even without a comment.|
| `string UnitAbbrev = "\u03bcs"; // "μs" `|	Allowed, but there's no reason to do this. |
| `string UnitAbbrev = "\u03bcs"; // Greek letter mu, "s"`	| Allowed, but awkward and prone to mistakes. |
| `string UnitAbbrev = "\u03bcs"; `|	Poor: the reader has no idea what this is. |
| `return '\ufeff' + Content; // byte order mark	`|Good: use escapes for non-printable characters, and comment if necessary. |

## Formatting
### Braces
Braces are used with `if`, `else`, `for`,` do` and `while` statements, even when the body is empty or contains only a single statement.
### Variable Declaration
#### Only have one variable per declaration
Every variable declaration (field or local) declares only one variable: declarations such as `int a, b;` are not used.

Exception: Multiple variable declarations are acceptable in the header of a `for` loop.
#### Declare variables when requried
Local variables are not habitually declared at the start of their containing block or block-like construct. Instead, local variables are declared close to the point they are first used (within reason), to minimize their scope. Local variable declarations typically have initializers, or are initialized immediately after declaration.

### Switch Statements
#### Indentation
As with all blocks, the contents of switch blocks are indented by 1 tab

### Deprecating Methods and Classes
If code classes or methods are replaced by newer ones or are no longer maintained. The best way to do this should be:
``` 
[Obsolete("Method1 is deprecated, please use Method2 instead.")] // YOu must include a message here to inform developers.
public void Method1()
{ … }
```
If you also need this to cause an error during compilaton instead of a warning (enforcing changes to be made) add `true` to the obsolete attribute like this ``` [Obsolete("Method1 is deprecated, please use Method2 instead.", true)] ```

Some parts have been adapted from (https://google.github.io/styleguide/javaguide.html) for C#

# Code Comments
To ensure that code is self-explainable, It is recommended to add code comments. In C#, Code comments are written after a double slash for single (`//`) line or a slash and asterisk (`/* */ `) for multiline comments. 
## Documentation
Classes, Methods and functions can be documented using C# XML documentation which is automatically activated by most C# ides whenever a ```///``` is typed above a class or method. Similar to HTML, XML makes use of tags which you can use to document your code. The description should be included in the `<summary>` tags.
