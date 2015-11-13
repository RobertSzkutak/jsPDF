#jsPDF MarkLogic Edition

Rename jspdf.min.js to jspdf.min.sjs if you are using a MarkLogic version earlier than 8.0-4.

If you choose to build this library, you may follow the original instructions to build it with one caveat: You MUST remove FileSaver.js, html2canvas, and adler32cs.js from /libs/ before building. Including any of these three currently breaks jsPDF within MarkLogic.

## Creating your first document

Create a PDF and store it within MarkLogic:

```javascript
declareUpdate();
var jsPDF = require('/lib/jspdf.min.sjs');
var doc = new jsPDF();
doc.text(20, 20, 'Hello world.');
doc.save('Test.pdf');
```

To verify:
```javascript
fn.doc('Test.pdf')
```

## Checking out the source

```bash
git clone --recursive git://github.com/MrRio/jsPDF.git
```

## Building

To build, simply run the 'make' command. This will fetch all npm and bower deps, then compile minified JS files.

## MarkLogic Edition Credits

Kevin Ford for extensively refactoring my first attempt at this project.

Paxton Hare for making code recommendations.

The many MarkLogicians who have reached out to me in support of this project.

## Credits

Big thanks to Daniel Dotsenko from [Willow Systems Corporation](http://willow-systems.com) for making huge contributions to the codebase. 

Thanks to Ajaxian.com for [featuring us back in 2009](http://ajaxian.com/archives/dynamically-generic-pdfs-with-javascript).

Everyone else that's contributed patches or bug reports. You rock.

## License

(MIT License)

Copyright (c) 2010-2014 James Hall, https://github.com/MrRio/jsPDF

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
