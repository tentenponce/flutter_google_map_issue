# Flutter 3.27.x and up issue on Google Maps

Simulate OpenGLRenderer issue on recent Flutter versions (3.27.x and up), but not happening on Flutter version 3.24.x. [Issue link](https://github.com/flutter/flutter/issues/160854)

## 3.27.x & 3.29.0 - has issue

<img src="demo/3.27.x.gif" width="200" alt="3.27.x demo">

## 3.24.x - no issue

<img src="demo/3.24.x.gif" width="200" alt="3.24.x demo">

## Getting Started

- Install [FVM](https://fvm.app/) to easily switch Flutter versions - Optional, as long as you can switch Flutter version
- Put your Google Map API key in `android/app/build.gradle`
- `fvm flutter run` - Or simply `flutter run` if you're not using FVM

## Replication Steps

> Note: Make sure you are using Flutter version 3.27.x (or 3.29.0). Otherwise, the issue will not happen.

- Fling the map anywhere
- Before the map stops, click the floating action button to navigate on a different screen
- Go back, map is frozen: cannot fling, drag, zoom, or anything

## Logs

These are the logs being shown after the replication steps

```plaintext
W/OpenGLRenderer(18241): dequeueBuffer failed, error = -110; switching to fallback
W/Looper  (18241): Slow Looper main: Long Msg: seq=936 plan=22:42:13.195  late=22ms wall=1009ms running=1ms h=android.view.Choreographer$FrameHandler c=android.view.Choreographer$FrameDisplayEventReceiver
W/OpenGLRenderer(18241): reserveNext failed, error = -2147483648 (Unknown error -2147483648)
```
