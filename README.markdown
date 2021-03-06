# Blade CLI

[![Build Status](https://liferay-test-01.ci.cloudbees.com/job/liferay-blade-cli/badge/icon)](https://liferay-test-01.ci.cloudbees.com/job/liferay-blade-cli/)

The Blade CLI is a command line java tool that can be used to help bootstrap Liferay 7 module development.

## Installation

Please refer to documentation on Liferay Developer Network here: https://dev.liferay.com/develop/tutorials/-/knowledge_base/7-0/installing-blade-cli

### How to Build Blade CLI Jar from Sources

Clone this repo, and then from the command line execute following command:

```
$ ./gradlew clean build -x check
```

## Usage

Once you have the blade cli installed you can see the list of commands just type
```
$ blade
```

Or ```java -jar com.liferay.blade.cli.jar``` if not using JPM.

Current available commands

### Create

The ```create``` command allows you to create new Liferay 7 module projects based on gradle.

```
$ blade create -t mvc-portlet helloworld
```

This will create a new helloworld portlet module project that contains an OSGi component built by a gradle script.
 To see all the options of the create command just run ```$blade create -h``` for all options.

 If you would like to see all available templates use `create -l` command.

 ```
 $ blade create -l
 ```

### Deploy

First, start Liferay 7 Portal, once it is running you can build your Liferay 7 module and deploy it

```
$ blade deploy build/libs/helloworld-1.0.jar
```

### Gradle Wrapper

In Liferay 7, Gradle is now the standard build tool for many of our projects.  It can be tedious to invoke the gradle wrapper if you have many nested subprojects.
The ```gw``` command allows you to invoke the gradle wrapper from any directory easily.

```
$ blade gw deploy
```

###  Help

Get help on a specific command

```
$ blade help create
```

###  Init

Initializes a new Liferay workspace.

```
$ blade init my-workspace
$ cd my-workspace
```

### Install

Installs a bundle into Liferay module framework.

```
$ blade install  
```

### Migrate Theme

Migrate a plugins sdk theme to new workspace theme project

```
$ blade migrateTheme my-theme
```

### Open   

Opens or imports a file or project in Liferay IDE.

```
$ blade open
```

###  Samples

[Liferay Blade Samples](https://github.com/liferay/liferay-blade-samples) contains examples of some of the most common integration points in Liferay 7.

You can use blade to grab any of the samples easily.

This will give you the list of samples available.

```
$ blade samples
```

This will get you the friendly url sample.

```
$ blade samples blade.friendlyurl
```

### Server

Start or stop server defined by your Liferay project


### Shell

Liferay 7 has a built-in gogo shell that can be accessed with telnet client on port 11311.  However, many times you just wish
to be able to run a gogo command remotely from the cmdline and return the results directly to the console.  Use the ```blade sh``` to do just that.

```
$ blade sh <gogo-command>
```

Some examples:

List all bundles running in the framework.
```
$ blade sh lb
```

Search for all services that provide javax.portlet.Portlet
```
$ blade sh services | grep javax.portlet.Portlet
```

### Update

This command updates blade to latest version

```
$ blade update
```

### Version

This command shows the current version of blade

```
$ blade version
```

## Release
Blade Tools is continuously built and released on [CloudBees](https://liferay-test-01.ci.cloudbees.com/job/liferay-blade-cli/).

[![Built on DEV@cloud](http://www.cloudbees.com/sites/default/files/Button-Built-on-CB-1.png)](http://www.cloudbees.com/foss/foss-dev.cb)

## License
All source to this project is available under [Apache 2.0 License](/LICENSE.txt)
