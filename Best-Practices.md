1. A function should *do one thing.* This applies whether you're using C# or JavaScript.
3. Use most recommendations made by ReSharper and StyleCop. Ignore most suggestions regarding documentation, per the book _Clean Code_, which says such things are redundant if you name your functions appropriately.
3. Dispose of _everything_ that implements **IDisposable** by wrapping with a `using { ... }` block.
4. Declare your variables as close to their first usage as possible. _Do not declare all your local variables at the top of a method._
5. Acquire a resource as late as possible, release it as soon as its safe.
6. Combining the previous two recommendations means you need to be aware of "deferred execution." If you are using **LinqToSql** to connect to your database, return your result set as an `ICollection<T>` or `IList<T>` instead of `IEnumerable<T>` and `IQueryable<T>`, or you will encounter errors if your data context is disposed [cref](http://stackoverflow.com/a/3894849/16454).

## Ajax considerations
Regarding the use of Ajax loading indicators:
  1. Your goal should be to maintain a level of speed that makes indicators unnecessary. However, "Plan on using some sort of animation if the action takes longer than 1s." —[Stack Overflow](http://stackoverflow.com/a/536318/16454)
  2. When you do need to use an indicator, use an HTML5 Canvas or Raphael.js SVG library instead of an animated gif. Gifs are pixelated, and don't look so great with the new "retina" displays or zoomable browsers.
  2. Some websites use a fade layer beneath an indicator to make the indicator  stand out better and prevent secondary input while the other operation is completing. We should avoid situations that would lock down on the user in such a way. Users don't like being corralled like that. The exception would be modal dialogs, but they should be used appropriately, as in where the input being requested would actually change the application's mode.

## ASP.NET
1. Never put your code in the web form. Never use `<%= Spaghetti.Code %>`. 
	1. Prefer an `OnItemDataBound` event handler when binding server-side grids.
	2. Prefer the Razor view engine when using MVC.
2. Always use Web Application Project instead of a Website Project. As of Visual Studio 2010, there is no longer an easy way to convert a Website Project to Web Application Project. Website Projects do not have the level of configuration available to Web Applications, and references are not retained.

## Repository Specifics
1. With Git's built-in branching, forking, and merging capabilities, you no longer have to have separate "trunk", "branches", or "tags" folders under your main repository. So just put your product's projects in the root.
2. When appropriate, reference issue numbers when you check in to GitHub. You can tag an issue using the pound sign followed by the number of the issue. Keywords “fixed/fixes” and “closed/closes” preceding the issue number will immediately change the issue’s status.
3. Corollary is this: Don't use the hash symbol when itemizing lists in wikis or issue comments, e.g. `#1 do this, and #2 do that`, as that will create unintended hyperlinks to the issues identified by those numbers.

## Use Code Metrics
Code metrics were introduced in Visual Studio 2008. Prior to that you had to use tools like SourceMonitor to get your metrics. Not all Visual Studio packages come with code metrics, so if yours doesn't, you can install the [extensions](http://visualstudiogallery.msdn.microsoft.com/9f35524b-a784-4dbc-bd7b-6babd7a5a3b3) for free.

Metrics will help you understand complexity and other factors that affect maintainability.  The following areas are closely related.

1. Use one class per file.
2. Only one namespace per file.
3. If you have more than 500 lines of code in your class, you need to refactor it.
4. If you have more than a half-dozen lines of code in your methods, it’s highly unlikely that those methods are “doing one thing” as they ought.
5. Use the guidelines extension and set your right margin at column 121  
   Historically people have constantly increased the character width of their lines of code as their monitor resolution has increased. In the last 10 years I’ve seen standards change from 80 characters to 100 characters to 120 characters. But 120 is probably a good place to stop. Chances are if your lines of code are that long, you’re either using names that are too long, or you are violating the [Law of Demeter](https://www.google.com/search?q=law+of+demeter).