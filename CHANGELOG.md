# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Comprehensive README documentation
- Troubleshooting section
- Development guidelines
- Contributing guidelines
- GitHub issue and PR templates
- CHANGELOG.md file

### Changed
- Improved project structure documentation
- Enhanced .gitignore file

## [1.0.1] - 2025-03-25

### Fixed
- Fixed clipboard integration for images - now properly sets PNG format to clipboard instead of file path
- Improved AppleScript implementation for better image handling

### Added
- Demo video (demo.mp4) to showcase functionality

### Changed
- Updated README with demo video link

## [1.0.0] - Initial Release

### Added
- Screenshot capture from Android devices via adb
- Screenshot capture from iOS devices via libimobiledevice
- Automatic clipboard integration for macOS
- Custom filename support
- Timestamp-based file naming
- Environment variable configuration for save path
- Command-line interface with options:
  - `-a` for Android device capture
  - `-i` for iOS device capture
  - `-s` for saving screenshots from all connected devices
  - `-h` for help information

### Features
- Cross-platform device support (Android & iOS)
- Automatic device detection
- Error handling for missing dependencies
- PNG format support
- macOS clipboard integration using AppleScript

[Unreleased]: https://github.com/sakebook/pbssc/compare/v1.0.1...HEAD
[1.0.1]: https://github.com/sakebook/pbssc/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/sakebook/pbssc/releases/tag/v1.0.0