The native-messaging-example-host-file (Chrome App here https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/docs/examples/api/nativeMessaging/host/, and see https://developer.chrome.com/extensions/nativeMessaging) is modified in several alternative ways.  A different Python module is used each time.  The aim is only to demonstrate the main ideas of the messaging process.

Code was tested on Python 2.7.6, for 'little endian'.  (Big endian machines will require zero(s) to be added in opposite order).  Note also that longer messages will need less padding with zeros for the returned 32-bit word length message.

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

