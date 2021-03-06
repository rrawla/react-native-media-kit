# react-native-media-kit

Html `<Video />` and `<Audio />` components from react-native for both iOS and Android. 

Supported media types:

​	iOS: Should be same as those supported by [MPMoviePlayerController](https://developer.apple.com/library/ios/documentation/MediaPlayer/Reference/MPMoviePlayerController_Class/)

​	Android: Shold be same as those supported by [ExoPlayer](https://github.com/google/ExoPlayer)

![](demo/demo.gif).

## Install

Run `npm install —-save react-native-media-kit@latest `

#### iOS

For now, just drag our ***react-native-media-kit.xcodeproj*** file into your Xcode project and link the **libreact-native-media-kit.a** library.

We're working on Cocoapods specs.

#### Android

Modify as follow:

**android/settings.gradle**

```
include ':react-native-media-kit'
project(':react-native-media-kit').projectDir = new File('../node_modules/react-native-media-kit/android')
```

**android/app/build.gradle**

```
dependencies {
    ...
    compile project(':react-native-media-kit')
}
```

**MainActivity.java**

```
import com.yoai.reactnative.media.MediaKitPackage;
...
protected List<ReactPackage> getPackages() {
    return Arrays.<ReactPackage>asList(
        new MainReactPackage(),
            new MediaKitPackage()
    );
}
```

## Usage

Just use it like the [HTML <video> element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

```
<Video
  style={{width: width, height: width / (16/9)}}
  src={'http://v.yoai.com/femme_tampon_tutorial.mp4'}
  autoplay={false}
  preload={'none'}
  loop={false}
  controls={true}
/>
```



### API

We provide a limited set of props and methods comparing to the  [HTML <video> element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

##### Properties

| key          | value                                    | iOS  | Android |
| ------------ | ---------------------------------------- | ---- | ------- |
| **src**      |                                          | OK   | OK      |
| **autoplay** | A Boolean attribute; if specified, the video automatically begins to play back as soon as it's ready | OK   | OK      |
| **preload**  | A String attribute: can be 'none', 'metadata'(iOS only), 'auto' | OK   | OK      |
| **loop**     | A Boolean attribute; if specified, we will, upon reaching the end of the video, automatically seek back to the start. | OK   | OK      |
| **controls** | A Boolean attribute; if specifid, will offer controls to allow the user to control video playback, including seeking, and pause/resume playback. | OK   | OK      |

##### Callbacks

| key                   |      | iOS  | Android |
| --------------------- | ---- | ---- | ------- |
| **onPlayerPaused**    |      | OK   | OK      |
| **onPlayerPlaying**   |      | OK   | OK      |
| **onPlayerFinished**  |      | OK   | OK      |
| **onPlayerBuffering** |      | OK   | OK      |
| **onPlayerBufferOK**  |      | OK   | OK      |
| **onPlayerProgress**  |      | OK   | OK      |

##### Methods

- pause
- play
- stop
- seekTo





***We're working on a more detailed documentation. Please wait.***

