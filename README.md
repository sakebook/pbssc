# pbssc
Provide screenshot and copy to clipboard.

You can get the device image from the CLI and copy it to the clipboard.

## Requirement
- macOS only
- [adb](https://developer.android.com/studio/command-line/adb)
- [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice)

## Setup
- Set environment variable `PBSSC_IMAGE_PATH` images save path to `.zshrc`.

```
export PBSSC_IMAGE_PATH=/YOUR/PATH
```

## Android device

```
% ./pbssc.zh -a
```

## iOS device

```
% ./pbssc.zh -i
```
