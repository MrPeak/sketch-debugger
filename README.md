[![Slack Status](http://slack.animaapp.com/badge.svg)](http://slack.animaapp.com)
[![apm](https://img.shields.io/apm/l/vim-mode.svg?maxAge=2592000)]()
[![GitHub stars](https://img.shields.io/github/stars/animaapp/cocoapowder.svg?style=social&label=Star&maxAge=2592000)]()
[![Twitter Follow](https://img.shields.io/twitter/follow/animaapp.svg?style=social&label=Follow&maxAge=2592000)](https://twitter.com/@animaapp)

# CocoaPowder
Breakpoints for Sketch Plugins.

<kbd>![](http://animaapp.s3.amazonaws.com/github/PluginDebugger/PluginDebugger.gif)</kbd>

## Motivation

Instead of following logs the busy console, breakpoints allows you follow your variables on script runtime.

## Integration

1. Drop [CocoaPowder.js](https://raw.githubusercontent.com/AnimaApp/CocoaPowder/master/CocoaPowder.js) in your Plugin folder.
2. ```@import 'CocoaPowder.js'``` into your `.cocoascript` files.
3. Run ```cocoapowderSetup();``` once in your script.
4. Add breakpoints with this ```cocoapowderBreakpoint(function (x) { return eval(x); });```

Example:  
```
@import 'CocoaPowder.js'

// Setup
cocoapowderSetup();

function sampleFunction() {
    var myVar = "Before breakpoint";

    // This is how you add a breakpoint
    cocoapowderBreakpoint(function (x) { return eval(x); });

    myVar = "After breakpoint";
    log('Done!');
}

var onRun = function(context) {
    sampleFunction();
}
```

## Deployment
Before deploying your code, make sure you remove breakpoints or call ```disableCocoaPowder();```.

## Contributing

Contributions are welcome 🎉

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull request** so that we can review your changes

## License

The MIT License (MIT)

Copyright (c) 2016 Anima App

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
