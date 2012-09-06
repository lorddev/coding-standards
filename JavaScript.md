# Make jQuery play nice with ASP.NET IDs
It seems every year or so, Microsoft decides to arbitrarily change their naming conventions for server-side controls as generated on the client-side. It used to be `parentControl_childControl`, and then it turned into something crazy with dollar signs and numbers, breaking any client-side code you may have used to reference controls by fully-qualified ID.

Although you can force your site to use a certain method via configuration settings, [I recommend](http://mustfollow.wordpress.com/2012/08/12/optimizing-jquery-selectors-for-asp-net-controls/) future-proofing your jQuery selectors.

Per [Encosia benchmarks](http://encosia.com/11-keystrokes-that-made-my-jquery-selector-run-10x-faster/), for a server-side TextBox control, the recommended method is

     $('input[id$=txtInput]');

Obviously you need to be aware of which HTML object each control translates to (e.g. LinkButton = `<a/>`, Button = `<input/>`, DropDownList = `<select/>`, Multiline Textbox = `<textarea/>`).