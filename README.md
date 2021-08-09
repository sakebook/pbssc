# pbssc
Provide screenshot and copy to clipboard.

You can get the device image from the CLI and copy it to the clipboard

https://user-images.githubusercontent.com/729101/128733918-10f68291-c746-4413-84d7-2aab61345fa4.mp4

## Requirement
- macOS only
- [adb](https://developer.android.com/studio/command-line/adb)
- [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice)

## Install

You can install pbssc with Homebrew.

```
% brew tap sakebook/tap && brew install pbssc
```

## Setup
- Set environment variable `PBSSC_IMAGE_PATH`. This is an images save path.

```
export PBSSC_IMAGE_PATH=/YOUR/PATH
```

## Android device

```
% pbssc -a
```

## iOS device

```
% pbssc -i
```
## Save only screenshot from connected devices

```
% pbssc -s
```
