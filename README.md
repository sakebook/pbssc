# pbssc

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![macOS](https://img.shields.io/badge/platform-macOS-lightgrey.svg)](https://www.apple.com/macos/)

**pbssc** (Provide screenshot and copy to clipboard) is a command-line tool that captures screenshots from connected Android and iOS devices and automatically copies them to your macOS clipboard.

Perfect for developers, QA engineers, and designers who frequently need to capture and share device screenshots during development and testing workflows.

## Features

- **Multi-platform support**: Capture screenshots from both Android and iOS devices
- **Automatic clipboard integration**: Screenshots are automatically copied to macOS clipboard
- **File saving**: Save screenshots to a specified directory with timestamp
- **Simple CLI interface**: Easy-to-use command-line options
- **Fast and lightweight**: Minimal dependencies and quick execution

## Demo

https://user-images.githubusercontent.com/729101/128733918-10f68291-c746-4413-84d7-2aab61345fa4.mp4

## Requirements

- **macOS only** (tested on macOS 10.15+)
- **Android devices**: [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb)
- **iOS devices**: [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice)

## Installation

### Homebrew (Recommended)

```bash
brew tap sakebook/tap && brew install pbssc
```

### Manual Installation

1. Download the `pbssc` script from this repository
2. Make it executable:
   ```bash
   chmod +x pbssc
   ```
3. Move it to a directory in your PATH:
   ```bash
   sudo mv pbssc /usr/local/bin/
   ```

### Dependencies Setup

#### For Android devices:
```bash
# Install Android SDK platform tools
brew install android-platform-tools
```

#### For iOS devices:
```bash
# Install libimobiledevice
brew install libimobiledevice
```

## Setup

Set the environment variable `PBSSC_IMAGE_PATH` to specify where screenshots should be saved:

```bash
export PBSSC_IMAGE_PATH=/path/to/your/screenshots
```

Add this to your shell profile (`.bashrc`, `.zshrc`, etc.) to make it permanent:

```bash
echo 'export PBSSC_IMAGE_PATH=/path/to/your/screenshots' >> ~/.zshrc
```

## Usage

### Basic Commands

#### Capture from Android device
```bash
pbssc -a
```
Captures a screenshot from the connected Android device, saves it, and copies to clipboard.

#### Capture from iOS device
```bash
pbssc -i
```
Captures a screenshot from the connected iOS device, saves it, and copies to clipboard.

#### Save screenshots from all connected devices
```bash
pbssc -s
```
Captures screenshots from all connected devices and saves them (without copying to clipboard).

### Advanced Usage

#### Custom filename
```bash
pbssc -a my-custom-screenshot.png
pbssc -i app-login-screen.png
```

#### Help
```bash
pbssc -h
```

### Example Workflow

1. Connect your Android or iOS device via USB
2. Enable USB debugging (Android) or trust the computer (iOS)
3. Run the appropriate command:
   ```bash
   # For Android
   pbssc -a
   
   # For iOS
   pbssc -i
   ```
4. The screenshot is automatically saved and copied to your clipboard
5. Paste anywhere with `Cmd+V`

## Troubleshooting

### Common Issues

#### "adb command not found"
```bash
# Install Android platform tools
brew install android-platform-tools

# Or add Android SDK to PATH
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

#### "idevicescreenshot command not found"
```bash
# Install libimobiledevice
brew install libimobiledevice
```

#### "Connected android device not found"
- Ensure USB debugging is enabled on your Android device
- Check device connection: `adb devices`
- Try reconnecting the device

#### "Connected ios device not found"
- Ensure you've trusted the computer on your iOS device
- Check device connection: `idevice_id -l`
- Try reconnecting the device

#### "Please set the PBSSC_IMAGE_PATH environment variable"
```bash
export PBSSC_IMAGE_PATH=/path/to/your/screenshots
mkdir -p $PBSSC_IMAGE_PATH
```

## Development

### Prerequisites
- macOS development environment
- Bash shell
- Connected Android/iOS devices for testing

### Testing
```bash
# Test Android functionality
adb devices
./pbssc -a

# Test iOS functionality
idevice_id -l
./pbssc -i
```

### File Structure
```
pbssc/
├── pbssc           # Main executable script
├── README.md       # This file
├── LICENSE         # Apache 2.0 License
└── .gitignore      # Git ignore rules
```

## Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add some amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Contribution Guidelines
- Follow existing code style
- Test your changes on both Android and iOS devices
- Update documentation as needed
- Add tests for new features

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb) for Android device communication
- [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice) for iOS device communication
- The open-source community for inspiration and support

## Support

- **Issues**: [GitHub Issues](https://github.com/sakebook/pbssc/issues)
- **Discussions**: [GitHub Discussions](https://github.com/sakebook/pbssc/discussions)
- **Homepage**: [https://github.com/sakebook/pbssc](https://github.com/sakebook/pbssc)
