The native-messaging-example-host-file (Chrome App [native messaging example] (https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/docs/examples/api/nativeMessaging/host/), and also [this link] (https://developer.chrome.com/extensions/nativeMessaging)) is modified in several alternative ways.  A different Python module is used each time.  The aim is only to demonstrate the main ideas of the messaging process.

Note: Code was tested on Python 2.7.6, for 'little endian'.  (For 'big endian', pad the returned message's length with the zeros to the left instead).  The required amount of this 'padding' will depend on the returned message's length.  Longer messages will need less padding of the returned 32-bit word length message.

----------------------

The following five files are alternatives to the 'native-messaging-example-host' file of the original Google example.  (Note: 'usingDecode' won't work with Python 3.)  Select the one you want to use, rename it 'native-messaging-example-host', and replace accordingly:

File usingStruct:  A skeletal version of the original native-messaging-example-host.  

File usingCodecs:  A version of native-messaging-example-host that uses the 'codecs' module.  Additionally, the message is saved to file.

File usingBinascii: A version that uses the 'binascii' module.

File usingBase64: Version of native-messaging-example-host that uses the 'base64' module. 

File usingDecode: This version is limited to Python 2.

----------------------

Folder 'App': The Google-provided example uses deprecated code.  I've therefore modified manifest.json and created background.js, so the example here is up-to-date.  A complete collection of the required files is provided.

Folder 'Host':  For completeness, Ie've included the important host files from the example's link here.  These files are all totally unchanged from the original example.
Note that com.google.chrome.example.echo.json should be in ~/.config/google-chrome/NativeMessagingHosts (or ~/.config/chromium/NativeMessagingHosts for Chromium), and the HOST_PATH should be modified to point to one of the 5 modifications.  Ensure that all file permissions are appropriate.

