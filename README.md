ab-test-framework
=================

a light ab test tool to render ab test result to file or output using html or json

## Install

Only git support now...
```
git checkout [this repository]
```

Install dependency

```
cd [path-to-this] && npm install
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

The output json will like:

```
[{ URL: 'http://192.168.1.1/upload/mov_bbb.mp4',
    TS: '20130822 21:53:10',
    N: '170',
    'Time taken for tests': '60.170 seconds',
    'Complete requests': '3134',
    'Failed requests': '0',
    'Write errors': '0',
    'Total transferred': '2525072828 bytes',
    'Requests per second': '52.09 [#/sec] (mean)',
    'Transfer rate': '40981.85 [Kbytes/sec] received',
    'Total min': '202',
    'Total mean1': '3152',
    'Total mean2': '1737.0',
    'Total median': '3108',
    'Total max': '19400' }
    ....(skip)}
```

And the output html will render the json to html table...

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
