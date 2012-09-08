## Code Formatting
7. Maintain indentation standards. This is crucial to readable code. Always use spaces instead of tabs. Default setting is 4 spaces, and this should be kept if possible, so as to remain compatible with other teams. However, some houses have adopted the 2-space standard because their code-base was created in the days of smaller screens and before people learned to write proper functions. (cref. “Functions should do one thing”)
9. In **C#**, curly braces should be on a new line. There are two exceptions:
	1.  Very short object initializers, e.g. `var message = new Literal { ID = "Message" };`
	2. Property declarations, whether automatic properties or simple getters/setters direct to private members.
10. Curly braces for delegates, collections, or object initializers should be indented 4 spaces (ME). Other specifications say differently, but following those specifications would require reformatting your indents every time you change a type or variable name, or even switch to `var` instead of explicit type declarations.

    ```c#
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