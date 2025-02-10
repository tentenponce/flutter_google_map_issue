# Flutter 3.27.x issue on Google Maps

Simulate OpenGLRenderer issue on Flutter version 3.27.x, but not happening on Flutter version 3.24.x.

## 3.27.x - has issue

![3.27.x recording](demo/3.27.x.gif)

## 3.24.x - no issue

![3.24.x recording](demo/3.24.x.gif)

## Getting Started

- Install [FVM](https://fvm.app/) to easily switch Flutter versions - Optional, as long as you can switch Flutter version
- Put your Google Map API key in `android/app/build.gradle`
- `fvm flutter run` - Or simply `flutter run` if you're not using FVM

## Replication Steps

> Note: Make sure you are using Flutter version 3.27.x. Otherwise, the issue will not happen.

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
