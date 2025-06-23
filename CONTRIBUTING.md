# Contributing to pbssc

Thank you for your interest in contributing to pbssc! This document provides guidelines and information for contributors.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [How to Contribute](#how-to-contribute)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing](#testing)
- [Reporting Issues](#reporting-issues)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to creating a welcoming and inclusive environment. Please be respectful and constructive in all interactions.

## Getting Started

### Prerequisites

- macOS development environment
- Bash shell knowledge
- Access to Android and/or iOS devices for testing
- Git for version control

### Development Setup

1. **Fork the repository**
   ```bash
   # Fork on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/pbssc.git
   cd pbssc
   ```

2. **Set up dependencies**
   ```bash
   # For Android testing
   brew install android-platform-tools
   
   # For iOS testing
   brew install libimobiledevice
   ```

3. **Set up environment**
   ```bash
   export PBSSC_IMAGE_PATH=/tmp/pbssc-test
   mkdir -p $PBSSC_IMAGE_PATH
   ```

4. **Make the script executable**
   ```bash
   chmod +x pbssc
   ```

## How to Contribute

### Types of Contributions

We welcome various types of contributions:

- **Bug fixes**: Fix issues reported in GitHub Issues
- **Feature enhancements**: Add new functionality
- **Documentation**: Improve README, add examples, fix typos
- **Testing**: Add test cases, improve test coverage
- **Performance**: Optimize existing functionality

### Before You Start

1. **Check existing issues**: Look for existing issues or discussions about your idea
2. **Create an issue**: For significant changes, create an issue to discuss the approach
3. **Get feedback**: Engage with maintainers and community members

## Pull Request Process

### 1. Create a Feature Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b bugfix/issue-number-description
```

### 2. Make Your Changes

- Follow the coding standards outlined below
- Add tests for new functionality
- Update documentation as needed
- Ensure your changes don't break existing functionality

### 3. Test Your Changes

```bash
# Test Android functionality (with device connected)
./pbssc -a

# Test iOS functionality (with device connected)
./pbssc -i

# Test help functionality
./pbssc -h

# Test error handling
unset PBSSC_IMAGE_PATH
./pbssc -a  # Should show error message
```

### 4. Commit Your Changes

Use clear and descriptive commit messages:

```bash
git add .
git commit -m "Add feature: custom screenshot resolution support

- Add -r flag for resolution selection
- Update help text with new option
- Add validation for resolution format
- Update README with usage examples"
```

### 5. Push and Create Pull Request

```bash
git push origin feature/your-feature-name
```

Then create a pull request on GitHub with:
- Clear title and description
- Reference to related issues
- Screenshots or examples if applicable
- Test results

## Coding Standards

### Bash Script Guidelines

1. **Use strict error handling**
   ```bash
   set -e  # Exit on error
   ```

2. **Quote variables**
   ```bash
   # Good
   if [[ -z "$variable" ]]; then
   
   # Bad
   if [[ -z $variable ]]; then
   ```

3. **Use meaningful function names**
   ```bash
   # Good
   check_exist_command_adb() {
   
   # Bad
   check_adb() {
   ```

4. **Add comments for complex logic**
   ```bash
   # Check if device is connected and accessible
   device_id=$(adb devices | sed '1d' | awk '{ print $1 }')
   ```

5. **Use consistent indentation** (2 spaces)

6. **Handle errors gracefully**
   ```bash
   if ! command -v adb &> /dev/null; then
     echo "adb command not found!" >&2
     exit 1
   fi
   ```

### Documentation Standards

1. **Update README.md** for user-facing changes
2. **Update help text** in the script for new options
3. **Add examples** for new features
4. **Update CHANGELOG.md** with your changes

## Testing

### Manual Testing Checklist

Before submitting a pull request, test the following scenarios:

#### Android Testing
- [ ] Device connected and recognized
- [ ] Screenshot capture works
- [ ] Image saved to correct location
- [ ] Image copied to clipboard
- [ ] Custom filename works
- [ ] Error handling for disconnected device

#### iOS Testing
- [ ] Device connected and recognized
- [ ] Screenshot capture works
- [ ] Image saved to correct location
- [ ] Image copied to clipboard
- [ ] Custom filename works
- [ ] Error handling for disconnected device

#### General Testing
- [ ] Help text displays correctly
- [ ] Environment variable validation
- [ ] Error messages are clear and helpful
- [ ] Script works from different directories

### Test Environment

Create a test environment:

```bash
# Create test directory
mkdir -p /tmp/pbssc-test
export PBSSC_IMAGE_PATH=/tmp/pbssc-test

# Test the script
./pbssc -h
```

## Reporting Issues

### Bug Reports

When reporting bugs, please include:

1. **Environment information**:
   - macOS version
   - Device type (Android/iOS)
   - Device OS version
   - pbssc version

2. **Steps to reproduce**:
   - Exact commands run
   - Expected behavior
   - Actual behavior

3. **Error messages**: Full error output

4. **Additional context**: Screenshots, logs, etc.

### Feature Requests

For feature requests, please include:

1. **Use case**: Why is this feature needed?
2. **Proposed solution**: How should it work?
3. **Alternatives**: Other ways to achieve the same goal
4. **Additional context**: Examples, mockups, etc.

## Questions and Support

- **GitHub Discussions**: For general questions and discussions
- **GitHub Issues**: For bug reports and feature requests
- **Documentation**: Check README.md and this file first

## Recognition

Contributors will be recognized in:
- GitHub contributors list
- Release notes for significant contributions
- Special mentions for major features or fixes

Thank you for contributing to pbssc!