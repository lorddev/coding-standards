1. A function should *do one thing.* This applies whether you're using C# or JavaScript.
2. Do not abbreviate variable names, properties, fields, functions, etc. Exceptions include CMS (`CmsPage`).
3. Use most recommendations made by ReSharper and StyleCop. Ignore most suggestions regarding documentation, per the book _Clean Code_, which says such things are redundant if you name your functions appropriately.

## ASP.NET Architecture
6. For web services, In lieu of .asmx files, .aspx WebMethods or WCF .svc files, use RequestRouters, loaded in the `Application_Start` method in `Global.asax.cs`. This keeps things cleaner and more RESTful.

## Ajax considerations
Regarding the use of Ajax loading indicators:
  1. Your goal should be to maintain a level of speed that makes indicators unnecessary. However, "Plan on using some sort of animation if the action takes longer than 1s." —[Stack Overflow](http://stackoverflow.com/a/536318/16454)
  2. Some websites use a fade layer beneath an indicator to make the indicator  stand out better and prevent secondary input while the other operation is completing. We should avoid situations that would lock down on the user in such a way. Users don't like being corralled like that. The exception would be modal dialogs, but they should be used appropriately, as in where the input being requested would actually change the application's mode.