# Liferay Gogo Scripts

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

The Liferay Gogo Scripts is a set of scripts to perform various administration tasks related to Liferay 7.x. These scripts use Gogo Shell and are intented to be building blocks for automation.

## Installation

Install the usual commands `telnet` and `expect` as prerequisites, then drop the *Liferay Gogo Scripts* files into a directory on your `$PATH`, and finally set execution permissions on the scripts. 

Read the [INSTALL](INSTALL.md) file for details.

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

Syntax:

```
gogo-shell <gogo-shell-statement>
``` 

Examples:

```
$ gogo-shell lb -s | grep com.liferay.portal.search
  179|Active     |   10|com.liferay.portal.search (4.0.7)
  180|Active     |   10|com.liferay.portal.search.api (1.1.2)
  181|Active     |   10|com.liferay.portal.search.elasticsearch (2.1.27)
  182|Active     |   10|com.liferay.portal.search.facet (2.0.11)
  183|Active     |   10|com.liferay.portal.search.web (2.0.2)
  184|Active     |   10|com.liferay.portal.search.web.api (1.0.2)
```

```
$ gogo-shell 'echo "Hello Gogo Shell"'
Hello Gogo Shell
```

#### gogo-shell-script

Execute a Gogo Shell script from a file located on the Liferay Server host.

Syntax:

```
gogo-shell <remote-gogo-shell-script-path>
```

#### gogo-groovy

Execute a Groovy statement, such as it would be executed via the script console of Control Panel. 

Syntax:

```
gogo-groovy <groovy-statement>
```

Example:

```
$ gogo-groovy 'println("Hello Groovy")'
Hello Groovy
```

#### gogo-groovy-script

Execute a Groovy script from a file located on the Liferay Server host.

Syntax:

```
gogo-groovy <remote-groovy-script-path>
```

#### gogo-bundle-get-version

Print the version of a particular bundle.

Syntax:

```
gogo-bundle-get-version <bundle-symbolic-name>
```

Examples:

```
$ gogo-bundle-get-version com.liferay.portal.search
4.0.7
```

If there are several bundles with the same symbolic name, each version is printed on a new line.

#### gogo-bundle-get-state

Print the state of a particular bundle.

Syntax:

```
gogo-bundle-get-version <bundle-symbolic-name> [<bundle-version>]
```

Examples

```
$ gogo-bundle-get-state com.liferay.portal.search
ACTIVE
```

```
$ gogo-bundle-get-state com.liferay.portal.search 4.0.7
ACTIVE
```

If the bundle version is not provided and there are several bundles with the same symbolic name, only the state of one of the bundle is printed.

#### gogo-bundle-start

Start a particular bundle.

Syntax:

```
gogo-bundle-start <bundle-symbolic-name> [<bundle-version>]
```

#### gogo-bundle-stop

Stop a particular bundle.

Syntax:

```
gogo-bundle-stop <bundle-symbolic-name> [<bundle-version>]
```

#### gogo-bundle-uninstall

Uninstall a particular bundle.

Syntax:

```
gogo-bundle-uninstall <bundle-symbolic-name> [<bundle-version>]
```

#### gogo-set-log-level

Set log level for a particular logger.

Syntax:

```
gogo-set-log-level <logger-name> <log-level>
```

Example:

```
$ gogo-set-log-level com.mycompany.mylogger DEBUG

```

#### gogo-reindex-all-search-indexes

Reindex all search indexes.

Syntax:

```
gogo-reindex-all-search-indexes
```

#### gogo-reindex-all-spell-check-indexes

Reindex all spell check indexes.

Syntax:

```
gogo-reindex-all-spell-check-indexes
```

#### gogo-clear-all-caches

Clear all caches.

Syntax:

```
gogo-clear-all-caches
```

This process
* clear content cached by this VM,
* clear content cached across the cluster,
* clear the database cache,
* and clear the direct servlet cache.

#### gogo-cleanup-portlet-preferences

Clean up portlet preferences.

Syntax:

```
gogo-cleanup-portlet-preferences
```

This process removes all orphaned portlet preferences that belong to page revisions. Portlet preferences that belong to a portlet that does not belong to a page revision will be removed. Portlet preferences that belong to runtime portlets will also be removed.

#### gogo-delete-dl-previews

Reset preview and thumbnail files for Documents and Media.

Syntax:

```
gogo-delete-dl-previews
```

#### gogo-initiate-shutdown

Display alert message to alert users before server shutdown.

Syntax:

```
gogo-initiate-shutdown <minutes> <custom-message>
```

Example:

```
$ gogo-initiate-shutdown 5 'Maintenance operation in progress'

```

This process :

* Display instantly an alert banner to the top of all pages for all user, including your custom message in addition to the Liferay shutdown alert standard message,

* and after the delay specified, display your custom message in full screen for to all users and prevent them to do any action.

This process does not stop the application server: you must do it yourself if you need it.

#### gogo-verify-plugin-table

Verify plugin table.

Syntax:

```
gogo-verify-plugin-table
```

#### gogo-verify-membership-policies

Verify membership policies.

Syntax:

```
gogo-verify-membership-policies
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
