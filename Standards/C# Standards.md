In many projects, _style guides_ and _coding standards_ are synonymous. In the CSW, however, we aim to differentiate between the two. We designate as “standards” those things which would make code comprehension quite difficult if they weren’t adopted broadly (don’t use Hungarian notation, don’t abbreviate, etc.), and as “style” those things which don’t necessarily made it difficult to understand the code, but would still improve if everyone were on the same page. Recommendations on the use of whitespace would fall in this category.

## Naming Conventions
1. Type names, constants and method names should use Pascal casing.
2. Camel casing applies to local variables declared inside a method, and arguments or parameters used in method declarations or constructors.
3. Hungarian notation should not be used. There has historically been some flexibility in terms of referencing server-side control IDs in ASP.NET. However, since these items are renamed by the ASP.NET engine and can be referenced using the [recommended jQuery selectors](JavaScript), use of these prefixes can be confusing (e.g. `txt_UserName` and `btn_Submit` render as  `<input type="text"/>` and `<input type="submit"/>` on the client-side.)
4. Method names should be verbs (optionally followed a direct object), as they describe an action, e.g. `stringReader.ReadLine()`.
5. Always use **C#** alias types (`string`, `int`, etc.). Some have said to use the .NET types (`System.String`, `System.Int32`, etc.) when calling static methods (like `Int32.Parse()`), but recent trends and tools discourage this.
6. Namespaces should be well thought-out and professional, following the methods used by Microsoft `Company.Product.Layer.Specialization` (e.g. `System.Web.UI.WebControls`)
8. Always use correct spelling and grammar in names, variables, comments, and database design.
9. Do not use abbreviations, either in object or method names, variables, or namespaces.
10. Use of well-known acronyms is permitted, but follow Microsoft's rules for capitalization.
      1. When used in PascalCasing or as the second word in camelCasing, only the first letter of an acronym should be capitalized.

      ```c#
      using System.Data.Sql;
      using System.Linq;
      ```
      2. Always capitalize both letters in two-letter acronyms.
      
      ```c#
      using System.IO;
      using System.Web.UI.WebControls;
      ```
      2. With the exception of the `Control` class and all objects that inherit from it, only the “I” in `Id` should be capitalized, as it is an _abbreviation_ for “identity” or “identifier” and not an actual acronym.
11. Do not add redundant or meaningless prefixes and sufixes to identifiers
      ```c#
      // BAD!
      public enum ColorsEnum {…}
      public class CVehicle {…}
      public struct RectangleStruct {…}
      ```

## Code Formatting
1. Always use curly braces for conditional statements. Never take the one-liner shortcut, or the one subline shortcut, as they are both vague.
2. Avoid ternary operators unless the statements are very short and easily readable, e.g.

    ```c#
    // This is ok.
    return isIdSpecified ? id : GetNewId();
    ```
3. Avoid nested ternary operators.
4. Never declare more than 1 namespace per file.
5. Avoid putting multiple classes in a single file.
6. Declare each variable independently – not in the same statement.
7. Use inline-comments to explain assumptions, known issues, and algorithm insights.
8. Do not use inline-comments to explain obvious code. Well written code is self documenting.
