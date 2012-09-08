1. Type names, constants and method names should use Pascal casing.
2. Camel casing applies to local variables declared inside a method, and arguments or parameters used in method declarations or constructors.
3. Hungarian notation should not be used. There has historically been some flexibility in terms of referencing server-side control IDs in ASP.NET. However, since these items are renamed by the ASP.NET engine and can be referenced using the recommended jQuery selectors, use of these prefixes can just be confusing (e.g. `txt_UserName` and `btn_Submit` render as  `<input type="text"/>` and `<input type="submit"/>` on the client-side.)
4. Method names should be verbs (optionally followed a direct object), as they describe an action, e.g. `stringReader.ReadLine()`.
5. Always use C# alias types (`string`, `int`, etc.). Some have said to use the .NET types (`System.String`, `System.Int32`, etc.) when calling static methods (like `Int32.Parse()`), but recent trends and tools discourage this.
6. Namespaces —> Use Microsoft spec
8. Always use correct spelling and grammar in names, variables, comments, and database design.