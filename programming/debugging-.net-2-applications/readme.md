# Treat Warnings As Errors
> "A perfect example is `CS0168` which is 'The variable `var` is declared by never used` .. nothing is more frustrating that spending 20 minutes punding through a 300 line poorly written method looking for what uses a particular variable, only to discover that nothing does."

[ReSharper](jetbrains.com/resharper) highlights these _as you type_, so there's no excuse to leave them in the code.  And ideally, your method should be [so small](https://github.com/daryllxd/lifelong-learning/blob/master/programming/clean-coders/03-functions.md), it's obvious to see them anyway.

> "..another is `CS1591`, 'Missing XML comment for publicly visible type or member'. This wonderful warning ensures that you're document all your code."

Again, R# warns of these, so no excuses.  I've also seen the XML comments in private code; I can see little benefit of this.  If you really need a comment, then use _normal_ `//comment syntax`, and **describe the _why_, not the _what**.

# Know Where Your Assemblies Load
The gist of this one is that the 'Base Address' (in project properties in VS) specifies the address that the 'assembly' loads at.  If there's something there, then it is 'rebased'.
> Even though you might think think that you don't have to worry about the DLL base address because managed code not have any actual CPU-specific assembly language in them by default, you still want to do it.   This is especially important if you are running NGen...

## Finding rebased DLLs:
* Start Process Explorer
* Select View DLLs from the View menu
* Select your process in the upper half of the main window

> If any DLLs show up highlighted in yellow, they have been relocated.