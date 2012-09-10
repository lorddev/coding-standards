## Code Formatting
1. Maintain indentation standards. Always use spaces instead of tabs. 
2. Related to indentation standards is the necessity of putting JavaScript in separate .js files rather than embedded in HTML. Script that’s nested in `<script/>` tags automatically have an increased indentation level.
9. In **JavaScript**, curly braces should be on the same line as the preceding condition or function declaration. Not only is this common practice for JavaScript, in which there is extra interest in keeping code minimized, but it is also necessary because of “implicit semicolon insertion” (see [Google JavaScript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)).
10. Speaking of implicit semicolon insertion... _don’t_. Always use explicit semicolons.
10. Personal preference is to indent lines of object initializers by 8 spaces and the closing curly brace by 4 (@lorddev).

    ```javascript#
    var data = {
            id: accountId,
            location: ipAddress
        };
    ```` 

11. Closing curly braces for anonymous functions should line up with the line in which they were declared. This indentation practice is even more crucial in the days of heavy jQuery usage, as often every single function in a file will be wrapped this way.

    ```javascript#
    $.each(results, function(item, index) {
        if (item.id == data.id && item.location != data.location) {
            // Todo: update user locations.
        }
    });
    ```

11. placeholder