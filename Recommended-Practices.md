This section is for items that have not quite attained broad appeal or widespread adoption it takes to be called "best" practices, but are _recommended_ nonetheless.

## ASP.NET/Ajax Architecture
6. When developing the web services which will be consumed by your Ajax calls, in lieu of .asmx files, .aspx WebMethods or WCF .svc files, use RequestRouters, which you can load in the `Application_Start` method in `Global.asax.cs`. This keeps things cleaner and more RESTful, as you won't have to use the file extensions in the URL.