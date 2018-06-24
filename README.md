# Liferay Gogo Scripts

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

The Liferay Gogo Scripts is a set of scripts to perform various administration tasks related to Liferay. These scripts use Gogo Shell and are intented to be building blocks for automation.

## Getting Started

To start, just install the usual commands `telnet` and `expect` then drop script files into a directory on your `$PATH`. 

### Prerequisites

The commands `telnet` and `expect` are the only prerequisites. They can be installed by the following commands:

* Debian, Ubuntu and other Linux distros supporting APT:

```
sudo apt-get install telnet
sudo apt-get install expect
```
* RHEL, Fedora, CentOS and other Linux distros supporting YUM:

```
sudo apt-get install telnet
sudo apt-get install expect
```
* macOS:

```
brew install telnet
brew install expect
```

### Installation

1. Download the [archive](https://github.com/slemarchand/liferay-gogo-scripts/archive/master.zip) from Github

```
wget https://github.com/slemarchand/liferay-gogo-scripts/archive/master.zip
```

2. Extract archive 

```
unzip master.zip
```

3. Copy scripts to the desired install directory, for example `/opt/liferay-gogo-scripts`

```
sudo mkdir -p /opt/liferay-gogo-scripts && sudo cp liferay-gogo-scripts-master/gogo-* /opt/liferay-gogo-scripts
```

4. Add the directory to the `$PATH` environment variable

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
