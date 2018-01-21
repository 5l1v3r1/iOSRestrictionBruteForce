# iOS Restriction Passcode Brute Force

[![Python2.7](https://img.shields.io/badge/Python-2.7-orange.svg?style=flat-square)](https://www.python.org/downloads/release/python-2714/) ![OS](https://img.shields.io/badge/Works%20On-Linux%20|%20macOS%20|%20Windows%20-green.svg?style=flat-square) ![iOS](https://img.shields.io/badge/Tested%20On%20iOS-9.3.5%20|%2010.0.1%20|%2011.2.1-green.svg?style=flat-square) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com) [![Code Climate](https://img.shields.io/codeclimate/maintainability/thehappydinoa/iOSRestrictionBruteForce.svg?style=flat-square)](https://codeclimate.com/github/thehappydinoa/iOSRestrictionBruteForce) [![Twitter](https://img.shields.io/twitter/follow/thehappydinoa.svg?style=flat-square&label=Follow%20Me)](https://twitter.com/thehappydinoa)

## Overview

This version of the application is written in Python, which is used to crack the restriction passcode of an iPhone/iPad takes advantage of a flaw in unencrypted backups allowing the hash and salt to be discovered.

![Restriction Passcode](docs/ios-restrictions.jpeg)

## DEPENDENCIES

This has been tested with [Python 2.7](https://www.python.org/downloads/release/python-2714/)

Requires [Passlib](https://passlib.readthedocs.io/en/stable/) Install with `pip install passlib`

## How to Use

1. Clone repository

  ```bash
   git clone https://github.com/thehappydinoa/iOSRestrictionBruteForce && cd iOSRestrictionBruteForce
  ```

2. Make sure to use [iTunes](https://www.apple.com/itunes/download/) or [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice) to backup the iOS device to computer

3. Run `ioscrack.py` with the webserver option

  ```
   python ioscrack.py -w
  ```

![GIF](docs/ioscrack.gif)

## Usage

```bash
usage: iOSCrack.py [-h] [-v] [-a] [-c] [-w] [-b folder]

a script which is used to crack the restriction passcode of an iPhone/iPad
through a flaw in unencrypted backups allowing the hash and salt to be
discovered

optional arguments:
  -h, --help            show this help message and exit
  -v, --verbose         increase output verbosity
  -a, --automatically   automatically finds and cracks hashes
  -c, --cli             prompts user for input
  -w, --webserver       creates webserver running flask
  -b folder, --backup folder
                        where backups are located
```

## How It Works

Done by using the [pbkdf2](http://www.ietf.org/rfc/rfc2898.txt) hash with the Passlib python module

1. Trys the [top 20 four-digit](http://www.datagenetics.com/blog/september32012/index.html) pins

2. Trys birthdays between 1900-2017

3. Brute force pins from 1 to 9999

## How to Protect Against

1. Encrpyt backups

2. Backup only on trusted computers

## Contributing

Best ways to contribute

- Star it on GitHub - if you use it and like it please at least star it :)
- [Promote](#promotion)
- Open [issues](https://github.com/thehappydinoa/iOSRestrictionBruteForce/issues)
- Submit fixes and/or improvements with [Pull Requests](http://makeapullrequest.com)

## Promotion

Like the project? Please support to ensure continued development going forward:

- Star this repo on [GitHub](action:files#disambiguate)
- Follow me

  - [Twitter](https://twitter.com/thehappydinoa)
  - [GitHub](https://github.com/thehappydinoa)

## Acknowledgments

- [yuejd](https://github.com/yuejd)

## LICENSE

[MIT License](LICENSE)
