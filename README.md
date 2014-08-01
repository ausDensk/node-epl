node-epl
--------

An EPL printer drawing library for nodejs

install
-------

```bash
npm install epl
```

example
-------

```js
var epl = require('epl')({ device : '/dev/usb/lp0' });

epl.start()
    .drawUPC('123456789999', 100 /* height */, 2 /* bar width */, true /* human readable */)
    .end()
    .print(function (err) {
        if (err) {
            return console.log(err);
        }

        console.log('success');
    });
```

api
---

### Constructor Options

* `device` - the output device or file to write lables to when calling the `print` method

```js
var epl = require('epl')({
    device : '/path/to/device'
});
```

### epl.setFont (fontNumber)
### epl.addText (text, size, advance)
### addTextCentered (text, size)
### epl.drawBarcode (text, height, size, humanreadable)
### epl.drawUPC (text, height, size, humanreadable)
### epl.drawLine (length, height, xor)
### epl.drawBox (length, height, stroke)
### epl.start ()

Start a new label. This must be called before adding anything to your label.

### epl.end ()

End a label. This must be called when you are finished adding elements to your label.

### epl.position (x, y)
### epl.move (x, y)
### epl.print (callback)
### epl.bookmark (name, xy)
### epl.recall (name)

license
-------

MIT

