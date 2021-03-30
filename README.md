# Why Clean Code?
  - Developers read code way much more than wirte it
  - The development process never stops, it can only be forzen for some time
  - Modification and maintenance of an existing application costs much more than writing a new one
  - A code reader has understand both overall concepts and implementation details. Sometimes, a reader needs to concentrate on concepts, sometimes on details

# Maintenance Cost
> Overall cost = Development Cost + Maintenance Cost

> Maintenance Cost = Cost of Understanding + Cost of Changes + Cost of Testing + Cost of Delivering

# Programming Metaprinciples
  - DRY or "Don't Repeat Yourself"
  - KISS or "Keep it Simple, Stupid"
  - YAGNI or "You Ain't Gonna Need"
  - SoC or "Separation of Concerns"
  - CQS or "Command-Query Separation"

# Naming API Members
- Correct naming is extremely important form the perspective of readability and as a consequence from the perspectice of maintenance
- Naming rules were different in the past
- Modern powerful PCs and managed languages with metadata make us able to develop very powerful IDEs which endow us by great power

## General Principle of Naming
- Intention-Revealing Names
- Disinformative Names
- Use Easily Readable Names
- No Encodings
    ```
    # Bad code
    i_age, i_count
    ```
    - No Jokes! Code is not a place for jokes!!!
    - Use Programming Terms
    ```
    [CustomerBuilder] is good name since a reader knows it is implemented via the "Builder" pattern.
    [CustomerFactory] implies that it is implemented via the "Factory" pattern
    ```

- Use Names from the Problem Domain
- Use Symmetry
    ```
    begin/end
    first/end
    locked/unlocked
    min/max
    next/previous
    old/new
    opend/closed
    visible/invisible
    source/target
    source/destination
    up/down
    ```
- Names of Classes
  1. Rule: "A name of a class should be a noun"
  2. Examples: Customer, Painter, DateTimeParser
  3. Avoid: Manager, Data, Info, CustomerData
- Names of Functions
  1. Rule: "A name of a function should be a verb"
  2. Examples: GetCustomer, Loaded, bool CanRedirect
  3. Boolean parameters: isCorrect, isBusy, CanExtract

## Naming Conventions in the .NET framework
There are two ways of naming any API members in .NET:
PascalCasing, camelCasing and Underscore Prefix
* Camel casing: In this standard, the first letter of the word always in small letter and after that each word starts with a capital letter. It is used for naming private and protected fields and for parameters.

Arguments and Local Variable
```sh
public string GetPosts(string postId  
{  
   int numberOfPost = 0;   
}  
```

* Pascal casing: In this the first letter of every word is in capital letter. It is used for naming Class, Method, Property, Interface, Public Member Variable, Namespace

Class
```sh
public partial class About : Page  
{  
   //...  
}
```

* Underscore Prefix (_underScore): For underscore ( __ ), the word after _ use camelCase terminology is used for Private Member Variable

Private Member Variable
```sh
private int _salary = 100; 
```
### Tips and Tricks
* Use intention-revealing names
* Don't use Disinformative of controversial names
* Use easily readable and pronounceable names
* Use English as coding language
* Don't rely on encoding such as Hungarian notation
* Don't be funny in your code
* Use well-known programming terms such as pattern names
* Use domain names
* Use sysmmetry in naming like Add and Remove, Push and Pop
* The wider the scope of a variable the longer its name can be
* Nouns for classes, verbs for functions
* Remember: code should be readable as a well-written prose
* Naming Enum: Always use PascalCasing as default naming standard. 
  1) Use a singular type name for an enumeration unless its values are bit fields.
  2) Use a plural type name for an enumeration with bit fields as values, also called flags enum.
  3) Do not use an "Enum" suffix in enum type names.
  4) Do not use "Flag" or "Flags" suffixes in enum type names.
  5) Do not use a prefix on enumeration value names.  
      ```sh
      enum MailType  
      {  
        Html,  
        PlainText,  
        Attachment  
      }  
    ```
* Naming Events: Events are associated with actions. Therefore, events are named with verbs. For example, Loaded, Clicked, and Printing.
  1) Give events names with a concept of before, current, and after, using the present and past tenses. Depending on the page, window, control, or class, the event names for a page can be, Initialized, PreRender, Rendering, PostRender, and Exited. A button event can be OnClick.
  2) Event handlers use "EventHandler" suffix, as shown in the following example:
  3) public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);
  4) Use two parameters named sender and e in event handlers.
  5) Name event argument classes with the "EventArgs" suffix. 

      ```sh
      event EventHandler StatusChanged;
      event EventHandler Closing;
      ```

* Naming Constants: Constants should have only the first letter uppercase

    ```sh
    public static int Age;
    public const int Max = 100; 
    ```
# Writing Clean Functions / Method
**TODO Update**
# .NET Core tips and tricks for coding
-	**Classes, methods, and variables should have understandable names:** The name
should explain everything the reader needs to know. There should be no need for an explanatory comment.
-	**Methods cannot have high complexity levels:** Cyclomatic complexity should be
checked so that methods do not have too many lines of code.
-	**Duplicate code should be avoided:** There is no reason for having duplicate code
in a high-level programming language like C#.
-	**Objects should be checked before usage:** Since null objects can exist, the code
must have null-type checking.
-	**Constants and enumerators should be used:** A good way for avoiding magic
numbers and text inside code is transforming this information into constants and
enumerators, which generally are more understandable.
-	**Unsafe code should be avoided:** Unless there is no other way to implement
code, unsafe code should be avoided.
-	**try-catch statements cannot be empty:** There is no reason for a try-catch
statement without treatment in the catch area.
-	**try-finally/using statements should always be used:** Even for objects where
Garbage Collector will take care of the disposed-of object, consider disposing of
objects that you were responsible for creating yourself.
-	**At least public methods should be commented:** Considering that public
methods are the ones used outside your library, they have to be explained for
their correct external usage.
-	**switch-case statements must have a default treatment:** Since the switch-case
statement may receive an entrance variable unknown in some cases, the default
treatment will guarantee that the code will not break in such a situation.
