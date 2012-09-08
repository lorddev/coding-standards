1. Type names, constnas and method names should use Pascal casing.
2. Camel casing applies to local variables declared inside a method, and arguments or parameters used in method declarations or constructors.
3. Hungarian notation should not be used. There has historically been some flexibility in terms of referencing server-side control IDs in ASP.NET. However, since these items are renamed by the ASP.NET engine and can be referenced using the recommended jQuery selectors, use of these prefixes can just be confusing (e.g. `txt_UserName` and `btn_Submit` render as  `<input type="text"/>` and `<input type="submit"/>` on the client-side.)
4. Method names should be verbs (optionally followed a direct object), as they describe an action, e.g. `stringReader.ReadLine()`.
5. Always use C# alias types (`string`, `int`, etc.). Some have said to use the .NET types (`System.String`, `System.Int32`, etc.) when calling static methods (like `Int32.Parse()`), but recent trends and tools discourage this.
6. Namespaces —> Use Microsoft spec
7. Maintain indentation standards. This is crucial to readable code. Always use spaces instead of tabs. Default setting is 4 spaces, and this should be kept if possible, so as to remain compatible with other teams. However, some houses have adopted the 2-space standard because their code-base was created in the days of smaller screens and before people learned to write proper functions. (cref. “Functions should do one thing”)
8. Always use correct spelling and grammar in names, variables, comments, and database design.
9. In C#, curly braces should be on a new line. There are two exceptions:
	1.  Very short object initializers, e.g. `var message = new Literal { ID = "Message" };`
	2. Property declarations, whether automatic properties or simple getters/setters direct to private members.
10. Curly braces for delegates, collections, or object initializers should be indented 4 spaces (ME). Other specifications say differently, but following those specifications would require reformatting your indents every time you change a type or variable name, or even switch to `var` instead of explicit type declarations.

    ``` C#
     var sqlParameters = new[]
        {
            new SqlParameter("@accountId", accountId),
            new SqlParameter("@loginSource", ipAddress),
        };
     using (var sqlCommand = new DataAccessObject())
     {
        sqlCommand.FillObject(sqlParameters, delegate(IDataReader reader)
            {
                while (reader.Read())
                {
                    // Todo: Put code here.
                }
            });
     }
    ```

11. Omit parenthesis when using object initializers, e.g. `var message = new Literal { ID = "Message" };`
12. test