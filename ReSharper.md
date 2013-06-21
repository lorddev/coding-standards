## Documentation issues
ReSharper will tell you to document everything. However, if you are properly naming and designing your objects and members, such comment blocks will simply be redundant, especially if you stick with the auto-generated versions. For example, 

    ```c#
    /// <summary>
    /// The Account Id.
    /// </summary>
    public long AccountId { get; set; }
    ```
I'd recommend going into your ReSharper/StyleCop settings and turning off most of the rules in the **Documentation** area. This is also consistent with the recommendations provided by Robert C. Martin In _Clean Code._

## Parameter can be of type 'IEnumerable<T>'
ReSharper's suggestion that a List or IList can be an IEnumerable instead may be a good idea to implement. Or it might not be. With objects that implement _deferred execution_ (such as **LinqToSql**), you might end up with your database connections opened and closed at unexpected times if you refactor an entire code flow to keep a result set as IEnumerable until the very last minute. Explicitly using IList<T> or ICollection<T> to pass a result set around can help you enforce query execution in the data layer, but make sure your team members know about this, or they might break things when they refactor.