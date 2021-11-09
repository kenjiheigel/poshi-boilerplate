# poshi-boilerplate
This repository contains the minimal configuration to begin writing and running Poshi tests through gradle.

## Prerequisites
 1. Java JDK 8
 2. [gradle](https://gradle.org/install/)

## Configuration

### Gradle Properties

#### Poshi Runner Version
To change the Poshi Runner version, update the `poshiRunnerVersion` property in [gradle.properties](https://github.com/CalumR23/poshi-boilerplate/blob/main/gradle.properties).

For updated and tested versions, please see the [Poshi Runner Change Log](https://github.com/liferay/liferay-portal/blob/master/modules/test/poshi/CHANGELOG.markdown)

#### Poshi Properties Files

Create a file (e.g. `poshi-ext.properties`) that will be used to set and override default Poshi properties.

In [gradle.properties](https://github.com/CalumR23/poshi-boilerplate/blob/main/gradle.properties), add the following to load the properties file into gradle:
```
poshiRunnerExtPropertyFileNames=poshi-ext.properties
```

Note that `poshiRunnerExtPropertyFileNames` can be a comma delimited list of properties files.

### Poshi Properties

Poshi Properties are necessary for configuring how tests are run within a particular Poshi project, and full list of properties is available [here](https://github.com/liferay/liferay-portal/blob/master/modules/test/poshi/poshi-properties.markdown).

In the created [Poshi Properties file](#poshi-properties-files), the following properties will be necessary to configure a project:
```
test.base.dir.name=path/to/local/poshi/files
```

#### Configuration for Chrome and Chromedriver
Add these properties to the created [Poshi Properties file](#poshi-properties-files)

```
browser.chrome.bin.file=path/to/chrome/binary # Optional, if not set the default Google Chrome will be used
browser.type=chrome

selenium.chrome.driver.executable=chromedriver # 'chromedriver.exe' for windows
selenium.executable.dir.name=path/to/browser/driver/executables
```

## Using Poshi
Poshi can be used using the following command syntax:
```
./gradlew -D<propertyValue> <task>
```

For help:
```
./gradlew help
```

To see available tasks (under "Poshi tasks"):
```
./gradlew tasks
```

### Running a test
To run standalone poshi in conjunction with this properties file, you can use the command
```
gradlew runPoshi -Dtest.name=MyTest#TestName
```