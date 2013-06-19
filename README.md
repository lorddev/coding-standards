Coding Standards
================

This is an open-source collaborative coding standards wiki intended to support developers who work in multiple languages. There is an emphasis on the coding styles recommended by ReSharper's default settings (that is, without the StyleCop plugin).

The entire project consists of *Markdown* files using GitHub's built-in Wiki format. Files may be edited in a text editor or directly in GitHub's online repository viewer, in the project's master branch. When ready to go live they will be merged into the wiki repository, which is hosted here an the GitHub at a different URI [Wiki](https://github.com/lorddev/coding-standards/wiki) tab. (If changes are inadvertently made to the wiki directly by developers with such permissions, please make sure you merge those changes into the project master.)

### Example cross-repo merging
In this scenario, the wiki is being pulled into the project's 1.0 branch (which reflects what's live), and then merged into the master branch, which is being used for development.

    git remote add wiki ../coding-standards.wiki
    git fetch wiki
    git checkout -b 1.0 wiki/master
    git checkout master                
    git merge 1.0
    git commit
    git push

(Normally we would do this in the other direction, editing in the master branch and then branching for release and copying to the wiki repo.)

### Note
To help search engines find our repo I'm just going to randomly shout "style guides" and "design guidelines". Thanks!
