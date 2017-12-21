# fancy protractor reporter
_Fork of protractor pretty html reporter with another feature of combining reports of several executions when using flake
All credit goes to the owner of protractor pretty html reporter_

[![Build Status](https://travis-ci.org/vdimikj/fancy-protractor-reporter.svg?branch=master)](https://travis-ci.org/vdimikj/fancy-protractor-reporter)
[![Latest Version](https://img.shields.io/github/tag/vdimikj/fancy-protractor-reporter.svg)](https://github.com/vdimikj/fancy-protractor-reporter)
[![NPM Version](https://img.shields.io/npm/v/fancy-protractor-reporter.svg)](https://npmjs.org/package/fancy-protractor-reporter)
[![NPM Monthly Downloads](https://img.shields.io/npm/dm/fancy-protractor-reporter.svg)](https://npmjs.org/package/fancy-protractor-reporter)

```
npm i fancy-protractor-reporter --save-dev
```

_NOTE: jasmine is set as a peer dependency_

## Advanced features
- Combining results of several reports

![screen shot](/imgs/test-failing-3-times.png)

[More Screenshots](#more-screenshots)

## Basic features
- Pass/Fail at a glance via navbar highlighting
- Bolds it('segment') within describe sentence for easy code searching
- Adds timing in milliseconds for total run time and spec run times
- Browser console logs for each spec
- Long running test support, report can be refreshed during test runs (see options)
- Suspect Line, best guess in the stack trace for your code (see options)
- Screenshots (see options)

![screen shot](/imgs/report.png)

[More Screenshots](#more-screenshots)

### Setup

protractor.conf
```
var FancyReporter = require('fancy-protractor-reporter').Reporter;

var fancyReporter = new FancyReporter({
    path: 'report/fancy' + new Date().toISOString().substring(0,19),
    screenshotOnPassed: false,
});

module.exports = {
    /* the rest of the object omitted */
    onPrepare: function() {
        jasmine.getEnv().addReporter(fancyReporter);
    },
    afterLaunch = () => {
      fancyReporter.combineReports();
    }
};
```


#### Reporter Options
For more options 

#### Examples
```
First Example - branch Example1
Second Example - branch Example2

Git location - https://github.com/vdimikj/protractor-example.git
```

[Preety protractor](https://www.npmjs.com/package/protractor-pretty-html-reporter)

## More Screenshots

### Combined results of several executions - success
![screen shot](/imgs/fail&success.png)

### Combined result of several executions - fail
![screen shot](/imgs/test-failing-3-times.png)

### Highlight the suspect line in your stacktrace
![screen shot](/imgs/report-test-suspect-line.png)

### Show a screen shot of the error page
![screen shot](/imgs/report-with-screenshot.jpg)

### Show console logs
![screen shot](/imgs/report-with-console-logs.png)
