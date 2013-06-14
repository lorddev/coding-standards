Welcome to the Coding Standards Wiki (CSW)!

This is a collection of **best practices** intended to be useful for career programmers and independent freelancers. There is a focus here on C#, but some concepts, such as "A function should do one thing" (from _Clean Code_'s [Bob Martin](http://blog.objectmentor.com/articles/2009/09/11/one-thing-extract-till-you-drop)) can translate to a hundred different programming languages.

I don't know about you, but I'm the kind of developer who always wants to get better. Whenever I find ways to improve my process or make my code cleaner, I try to implement that knowledge right away. Having worked on several different projects with several different teams, there are certain best practices that can be identified that would apply to all sorts of projects. The goal here will not be to water down to the lowest common denominator, but to steer towards a level of cleanliness that encourages innovation and facilitates maintenance and readability.

We want to differentiate between those things people do out of habit, and those things people do because it's a pattern they learned, and there's a reason for doing it that way. It is acknowledged that some people have different preferences&mdash;say, on how or whether to prefix private members. But there are broader issues which can impact your ability to collaborate with others in a big way.

### No developer is an island.
Your code should reflect an understanding of that. **Write code that you wouldn't be embarrassed about if your favorite nerd hero saw your last check-in.** It is practically a crime to leave your code in such a level of disarray under the assumption that you'll either clean it up later or always be the only one dealing with it. That's called [technical debt](http://www.codinghorror.com/blog/2009/02/paying-down-your-technical-debt). If another developer has to patch in an enhancement or find a bug, you don't want them to spend so much time trying to unravel spaghetti code that they might as well have started from scratch.

## The honor of your participation is requested...
The built-in Markdown compatibility and Git versioning make GitHub an ideal place for a collaborative standards project, as well as the wide adoption of GitHub itself by open-source programmers. If you search for "coding standards" on GitHub, there are only a few repositories, and they are pretty much project-specific, so it's a wide-open "market" of sorts.

This is your chance to promote universal action regarding your favorite pet peeve! Make your voice heard! Maybe we can start something here and have the kind of effect that would help educate people around the world and reduce the frequency of messy spaghetti code we'll encounter in the future!

You can either fork and issue pull requests, cloning the [Wiki repository](https://github.com/lorddev/coding-standards.wiki.git) and editing with your favorite Markdown editor. If you don't feel like doing all that, feel free to just create an issue with your suggestions. We look forward to hearing from you!

### Recommended apps for Markdown:

- Byword (OS X, iOS)
- SublimeText (OS X, Windows, Linux)
- WriteMonkey (Windows)