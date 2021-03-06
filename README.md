# autocomplete-java

Autocomplete-plus provider for Java. Current features:

* Complete package and class names
* Import classes
* Organize imports
* Examine public methods and properties of a class or instance and use them as snippets
* Crude determination of instance class (still a quick hack)
* Predictive suggestions (remembers previous selections)

TODO for v1.0.0:

* Unit tests
* [Autocomplete constructors](https://github.com/keskiju/autocomplete-java/issues/2)
* [Show inherited methods in method suggestions](https://github.com/keskiju/autocomplete-java/issues/6)
* [Support for multiple project folders](https://github.com/keskiju/autocomplete-java/issues/9)
* Fine tuning and small fixes

Some planned future features:

* [Autocomplete implementations of getter and setter methods](https://github.com/keskiju/autocomplete-java/issues/3)
* [Autocomplete implementations of overriding methods](https://github.com/keskiju/autocomplete-java/issues/4)
* [Intelligent determination of instance class](https://github.com/keskiju/autocomplete-java/issues/8)
* ... See all open issues at [GitHub issues](https://github.com/keskiju/autocomplete-java/issues)

Official page for package at atom.io: [autocomplete-java](https://atom.io/packages/autocomplete-java)

## Preview

![Screenshot](https://raw.github.com/keskiju/autocomplete-java/master/screenshot.gif)

## Usage

Configure classpath via a .classpath file that is placed at the root directory of your project. For example:

    ./src:./classes:./lib/*

You can also alter autocomplete behavior with package settings.  

NOTE:
* The package requires that either JAVA_HOME environment variable is set or JDK tools (javap, jar) are found in path. Alternatively you can set JAVA_HOME in package settings.
* The package requires compiled classes to function, but it does not compile classes from source. Use other tools for compiling.
* If you compile classes manually, disable the 'refresh class on save' setting and run 'refresh project' manually after compilation (ctrl-alt-shift-R). Also try to avoid running refresh command and build scripts at the same time.
* **Type determination is still a quick hack and it will be improved in the future. If the package fails to determine instance class automatically, you can still examine methods with a class name if you know the class yourself (e.g. ArrayList.con...). Note also that scanning all classes in classpath (full refresh) might take a few minutes.**

## Tips

At first, compile all your classes using your favorite build tool, and start your app. While editing java source files, lint and compile classes automatically with [linter-javac](https://atom.io/packages/linter-javac), and the autocomplete-java package will refresh changed classes automatically on save. You can also reload changed classes automatically in JVM with [spring-loaded](https://github.com/spring-projects/spring-loaded) or some other JVM agent. This way you can develop your app while the app is running.

NOTE: Linter-javac performs currently ok only on small projects ([linter-javac#38](https://github.com/AtomLinter/linter-javac/issues/38), [linter-javac#44](https://github.com/AtomLinter/linter-javac/issues/44)). On a larger project you might want to use some other tool to compile your files on save instead of linter-javac, at least for now.

NOTE: Error in one class may prevent compilation of multiple classes. Therefore once you fix an error, multiple classes might be recompiled at once. So sometimes you might have to run 'project refresh' manually after you fix an error (ctrl-alt-shift-R). See issue [#19](https://github.com/keskiju/autocomplete-java/issues/19).

## Contribute

Contributions are welcome. Please comment on [issues](https://github.com/keskiju/autocomplete-java/issues) you would like to contribute to, or add feature requests of your own.
