## Documentation issues
ReSharper will tell you to document everything. However, if you are properly naming and designing your objects and members, such comment blocks will often be nothing but redundant, especially if you stick with the ones it generates automatically. E.g.
    ```c#
    /// <summary>
    /// The Account Id.
    /// </summary>
    public long AccountId { get; set; }
    ```
_Really?_

I'd recommend going into your ReSharper/StyleCop settings and turning off the most of the items in the Documentation area. This is also consistent with the recommendations provided by Robert C. Martin In _Clean Code._