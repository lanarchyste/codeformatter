# CodeFormatter

[![Build status](https://ci2.dot.net/job/dotnet_codeformatter/job/master/job/innerloop/badge/icon)](https://ci2.dot.net/job/dotnet_codeformatter/job/master/job/innerloop/)

CodeFormatter is a tool that uses Roslyn to automatically rewrite the source to
follow our coding styles, which are [documented here][corefx-coding-style].

[corefx-coding-style]: https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md

## Prerequisites

In order to build or run this tool you will need to have Microsoft Build Tools
2015 installed.  This comes as a part of [Visual Studio 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs).

## Installation

Download binaries from [GitHub Releases](https://github.com/dotnet/codeformatter/releases)

## Usage

In order get the usage, simply invoke the tool with no arguments:

```
$ .\CodeFormatter.exe
CodeFormatter <project or solution> [<rule types>] [/file:<filename>] [/nocopyright] [/c:<config1,config2> [/copyright:file]
    <rule types> - Rule types to use in addition to the default ones.
                   Use ConvertTests to convert MSTest tests to xUnit.
    <filename>   - Only apply changes to files with specified name.
    <configs>    - Additional preprocessor configurations the formatter
                   should run under.
    <copyright>  - Specifies file containing copyright header.
```

## Rules

```
BraceNewLine         :Ensure all braces occur on a new line
Copyright            :Insert the copyright header into every file
NewLineAbove         :Ensure there is a new line above the first namespace and using in the file
CustomCopyright      :Remove any custom copyright header from the file
UsingLocation        :Place using directives outside namespace declarations
UnicodeLiterals      :Use unicode escape sequence instead of unicode literals
ExplicitVisibility   :Ensure all members have an explicit visibility modifier
IllegalHeaders       :Remove illegal headers from files
FormatDocument       :Run the language specific formatter on every document
ExplicitThis         :Remove explicit this/Me prefixes on expressions except where necessary
ReadonlyFields       :Mark fields which can be readonly as readonly
FieldNames           :Prefix private fields with _ and statics with s_
```

## Contributing

We follow the same contribution process that 
[corefx is using][corefx-contributing].

[corefx-contributing]: https://github.com/dotnet/corefx/wiki/Contributing
