# Liferay Gogo Scripts

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

The Liferay Gogo Scripts is a set of scripts to perform various administration tasks related to Liferay. These scripts use Gogo Shell and are intented to be building blocks for automation.

## Installation

Install the usual commands `telnet` and `expect` as prerequisites, then drop the *Liferay Gogo Scripts* files into a directory on your `$PATH`. 

Read the [INSTALL.md](INSTALL.md) file for details.

## Usage

### Configuration

All of the scripts can be configured by the following environment variables:

* `GOGO_HOST`: The host used to connect to Gogo Shell. If the variable is not set, the host used is `localhost`.

* `GOGO_PORT`: The port used to connect to Gogo Shell. If the variable is not set, the host used is `11311`.

### Scripts

#### gogo-shell

#### gogo-groovy

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
