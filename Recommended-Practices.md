This section is for items that have not quite attained broad appeal or widespread adoption it takes to be called "best" practices, but are _recommended_ nonetheless.

## ASP.NET Architecture
6. For web services, In lieu of .asmx files, .aspx WebMethods or WCF .svc files, use RequestRouters, loaded in the `Application_Start` method in `Global.asax.cs`. This keeps things cleaner and more RESTful.