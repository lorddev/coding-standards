The [Google C++ Style Guide](http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml) begins:

> Every major open-source project has its own style guide: a set of conventions (sometimes arbitrary) about how to write code for that project. It is much easier to understand a large codebase when all the code in it is in a consistent style.
> 
> “Style” covers a lot of ground, from “use camelCase for variable names” to “never use global variables” to “never use exceptions.” This project holds the style guidelines we use for Google code. If you are modifying a project that originated at Google, you may be pointed to this page to see the style guides that apply to that project.

Our aim with the CSW is to provide not only general style guidelines, but cross-platform principles and best practices that independent developers might not otherwise be exposed to. There are certain "rules" which would apply not only to one particular project, but would directly affect your ability to find your bearings if you come late to an existing project--or conversely, to deliberately manage a product in a way that would make it easier for late-comers to step onboard and be productive. Specifically, you'll be ensuring clean code and doing things the right way.

## Team Rules.
Our sections on style recognize that teams may have different rules. For example, I've worked with some teams in which private fields were prefixed `m_`, others where they are prefixed `_`, and then the StyleCop rules say not to prefix at all, and to distinguish between private members and method arguments by using `this.` to reference the class fields. But then I’ve worked on products in which the use of `this.` was actually not allowed (not a good team, by the way).

So as Uncle Bob Martin says: “Team Rules” (i.e. the rules of the team overrule your personal preferences). So you need to be ready to change your IDE settings when you switch teams. But we’re hoping to help people minimize the number of changes they’ll have to make, since that would become quite difficult if you are participating in a lot of different teams. For this reason, we will probably emphasize the ReSharper defaults more often than StyleCop.

## Don’t Fight the IDE
Related to changing “team rules” all the time, there is the idea of how many changes you will need to make to the default installation of your IDE. There is a well-known principle called “[Don’t fight the IDE](http://stackoverflow.com/questions/638561/what-is-the-proper-way-to-format-code/638573#638573).” You’ll end up pretty frustrated if you have to constantly tell your style guide tools to ignore machine-generated code (e.g. classes associated with LinqToSql DBMLs). Alternatively, the code auto-generated by ReSharper’s out-of-the-box configuration is going to look quite different from code auto-generated by Visual Studio. Furthermore, in order to work well with developers who don’t have ReSharper, you’ll need to find a balance.

See our [[ReSharper]] guide for more on this.

## Simplicity
A function should do one thing.

In general, a class should not have more than 500 lines of code.

In any context, in a code editor, you should be able to see the ending curly brace from its opener, and shouldn't have to scroll your window to see the boundaries of your current code block.

(In Visual Basic, this applies to `Using` statements, `If ... Then ... EndIf`, etc.)
