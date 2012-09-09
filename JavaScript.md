# JavaScript as Source Code
In the last 8 years since the introduction of Ajax, I have witnessed an massive evolution in the adoption and frequency of client-side code for web apps of all sorts. With libraries like jQuery and the adoption of HTML5 by most major browsers, JavaScript is growing even faster. The recommendations we include here address how we can treat our JavaScript more like source code and less like sporadic and random inserts of repeating script snippets throughout our source.

## Treat Your Functions Like Objects
JSON provides a nice bridge for understanding JavaScript code blocks in an object-oriented manner. Just as we avoid repeating code and multiple classes per file in our C# code, we should do the same with our JavaScript. Functions nested inside other functions can become private methods. They can be exposed as public methods using the `this` keyword, e.g.

    ```javascript
    function OrientedObject(newId) {
        var _id = newId;
        this.publicMethod = function() {
            return _id;
        };
    }
    
    var oriented = new OrientedObject(123);
    alert(oriented.publicMethod());
    ```

## Import your references
The `$.cachedScript()` example in [jQuery’s documentation](http://api.jquery.com/jQuery.getScript/) is a great example of how we can make sure our code dependencies are loaded at the top of a file, just as we do so in our C# code.

## Make jQuery play nice with ASP.NET IDs
It seems every year or so, Microsoft decides to arbitrarily change their naming conventions for server-side controls as generated on the client-side. It used to be `parentControl_childControl`, and then it turned into something crazy with dollar signs and numbers, breaking any client-side code you may have used to reference controls by fully-qualified ID.

Although you can force your site to use a certain method via configuration settings, [I recommend](http://mustfollow.wordpress.com/2012/08/12/optimizing-jquery-selectors-for-asp-net-controls/) future-proofing your jQuery selectors.

Per [Encosia benchmarks](http://encosia.com/11-keystrokes-that-made-my-jquery-selector-run-10x-faster/), for a server-side TextBox control, the recommended method is to use the "ends-with" (`$=`) selector, in combination with the tagName, e.g. `$('input[id$=txtInput]');`

This is so much friendlier than using the server-side `ClientScriptManager.RegisterClientScriptBlock()` methods.

Obviously you need to be aware of which HTML object each control translates to (e.g. LinkButton = `<a/>`, Button = `<input/>`, DropDownList = `<select/>`, Multiline Textbox = `<textarea/>`).

## Consider nesting your page-specific JS files underneath the .aspx
By editing your .csproj files manually, you can set the `<DependsUpon/>` tag to force your page-specific .js files to nest underneath your .aspx files just as your .cs and .designer.cs files do. This is good design for page-specific scripts as it keeps everything together in your Solution Explorer.