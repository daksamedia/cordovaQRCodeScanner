# cordovaQRCodeScanner
This repository demonstrates a QR code scanner based on the plugin cordova-plugin-qrscanner.

## Code Sample 

First add the plugin

```
cordova plugin add cordova-plugin-qrscanner
```

QRScanner is then globally available and can be used as follows

```js
QRScanner.scan(displayContents);

function displayContents(err, text){
    if(err){
        console.log(err);
    } else {
        // The scan completed, display the contents of the QR code:
        alert(text);
    }
}

// Make the webview transparent so the video preview is visible behind it.
QRScanner.show(function(status){
    console.log(status);
});
```

The result looks like this

![Cordova QR](https://github.com/benni1371/cordovaQRCodeScanner/blob/master/qr.png)

## Notes

The plugin seems to be a little unstable. If you start from scratch please add `worker-src 'self' blob:` to the Content-Security-Policy meta-tag in the HTML file.

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
