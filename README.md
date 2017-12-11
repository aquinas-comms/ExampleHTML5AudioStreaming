## Audio streaming app

V2.0 of the streaming app.  Very much in development

### Notes

Original inspiration: http://www.joeldare.com/wiki/play_an_mp3_audio_stream_in_phonegap

#### PhoneGap/Cordova

As no PhoneGap API's are used... just pure JavaScript, there is no PhoneGap / Cordova project included. Feel free to just use the contents of the `www` folder in a new project instead.

#### Background Audio

If you need background audio, you will need to add the supported modes in your `<Projectname>-info.plist` (in this case, `ExampleHTML5AudioStreaming-Info.plist`):

	<key>UIBackgroundModes</key>
    	<array>
        	<string>audio</string>
    	</array>

Also important to note, since iOS6, you must explicitly set the AVAudioSessionCategory.

http://stackoverflow.com/a/12414719/878602

First, import AVFoundation into your `AppDelegate.m` `#import <AVFoundation/AVFoundation.h>`

Then add the following to `application:(UIApplication*)application didFinishLaunchingWithOptions:(NSDictionary*)launchOptions`

```objective-c
AVAudioSession *audioSession = [AVAudioSession sharedInstance];
BOOL ok;
NSError *setCategoryError = nil;
ok = [audioSession setCategory:AVAudioSessionCategoryPlayback error:&setCategoryError];
```

*It is also important to note that background audio does* **not** *work in the iOS Simulator...* **only** *on an actual device*

## License

The MIT License

Copyright (c) 2011 Tommy-Carlos Williams (github.com/devgeeks)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
