# Changelog
All notable changes to this project will be documented in this file.

## 1.1.2 - 2019-01-11
### Removed
- Check for our servers, as we changed the way we monitor CPU usage

## 1.1.1 - 2019-01-02
### Fixed
- Location of the hostname check, to decrease the amount of email we get from Monit
- Readability, to match the shell style guide from Google

## 1.1.0 - 2018-12-29
### Added
- Check if the skip is running on our servers and disable Monit if it is
- Feature to skip image optimization
  Ideal feature if you just want to create `.gz` and `.br` files without killing
  your CPU.

### Fixed
- USAGE message, which was still displaying the old name of this script

## 1.0.0 - 2018-11-23
### Added
- This CHANGELOG file, to hopefully improve the way I handle Github commits and whatnot
- README file with proper information about this script
- LICENCE file for GPLv2
- Initial release

*The format of this changelog file is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).*
