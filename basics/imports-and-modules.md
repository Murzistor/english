# Imports and modules

For a simple hello world program in D, `import`s are needed.
The `import` statement makes all public functions
and types from the given **module** available.

The standard library, called [Phobos](https://dlang.org/phobos/),
is located under the **package** `std`
and its modules are referenced through `import std.MODULE`.

The `import` statement can also be used to selectively
import certain symbols of a module:

    import std.stdio : writeln, writefln;

Selective imports can be used to improve readability by making
it obvious where a symbol comes from, and also as a way to
prevent clashing of symbols with the same name from different modules.

An `import` statement does not need to appear at the top of a source file.
It can also be used locally within functions or any other scope.

### Imports match directories and files

Compared to other module system, is D's module system entirely based on files.
For example, `my.cat` always refers to a file `cat.d` in the folder `my`,
where the folder needs to be in the current working directory or be a folder
in one of the explicitly specified directory imports (`-I`).
Lastly, to ease splitting up modules, instead of `cat.d`,
a folder `cat` could be used as well.
The D compiler would then try to load `my/cat/package.d` instead of `my/cat.d`.

## {SourceCode}

```d
void main()
{
    import std.stdio;
    // or import std.stdio : writeln;
    writeln("Hello World!");
}
```
