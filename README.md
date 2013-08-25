ab-test-framework
=================

a light ab test tool to render ab test result to file or output using html or json

## Install

Only git support now...
```
git checkout [this repository]
```

## Usage

1. Prepare the config file that contains the test paths

ex: 

```
$ vi test.cfg
URL[0]=http://www.abc1.def.com/path/file.html
URL[1]=http://www.abc2.def.com/path/file.html
URL[2]=http://www.abc3.def.com/path/file.html
```

2. Do the benchmark

```
$path-to-this/bin/abtester test.cfg result.log
```

3. Do the parsing

```
$path-to-this/bin/abparser result.log

or

$path-to-this/bin/abparser result.log -j

or

$path-to-this/bin/abparser result.log -t result.csv
```

## Help page

```
$ abparser --help

  Usage: abparser [options]

  Options:

    -h, --help             output usage information
    -V, --version          output the version number
    -s, --source [source]  The source file for parsing
    -t, --target [target]  The target file path for output
    -j, --json             Use json output not html table
```
