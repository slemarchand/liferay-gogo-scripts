# Installing Liferay Gogo Scripts

tl;dr Just install the usual commands `telnet` and `expect` then drop script files into a directory on your `$PATH` and finally set execution permissions on the scripts. 

## Prerequisites

The commands `telnet` and `expect` are the only prerequisites. They can be installed by the following commands:

* Debian, Ubuntu and other Linux distros supporting APT:

```
sudo apt-get install telnet
sudo apt-get install expect
```
* RHEL, Fedora, CentOS and other Linux distros supporting YUM:

```
sudo yum install telnet
sudo yum install expect
```
* macOS with [Homebrew](https://brew.sh/):

```
brew install telnet
brew install expect
```

## Installation

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

4. Set execution permissions on the scripts

```
sudo chmod a+x /opt/liferay-gogo-scripts/*
```

5. Add the directory to the `$PATH` environment variable
