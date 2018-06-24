# Liferay Gogo Scripts

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

The Liferay Gogo Scripts is a set of scripts to perform various administration tasks related to Liferay. These scripts use Gogo Shell and are intented to be building blocks for automation.

## Installation

Install the usual commands `telnet` and `expect` as prerequisites, then drop the *Liferay Gogo Scripts* files into a directory on your `$PATH`, and finally set execution permissions on the scripts. 

Read the [INSTALL.md](INSTALL.md) file for details.

## Usage

### Configuration

All the scripts can be configured by the following environment variables:

* `GOGO_HOST`: The host used to connect to Gogo Shell. If the variable is not set, the host used is `localhost`.

* `GOGO_PORT`: The port used to connect to Gogo Shell. If the variable is not set, the host used is `11311`.

### Error management

All the scripts return proper exit status:

* in case of success the return code is `0`,

* and in case of failure, the return code is `1`.

Furthermore, when an error occurs, the error message is printed to the error output.

### Scripts

#### gogo-shell

Execute a Gogo Shell statement, such as it would be executed via the interactive shell.

```
gogo-shell <gogo-shell-statement>
```

#### gogo-groovy

Execute a Groovy statement, such as it would be executed via the script console of Control Panel. 

```
gogo-groovy <groovy-statement>
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
