# poshi-boilerplate
This repository contains the minimal configuration to begin writing and running Poshi tests through gradle.

## Prerequisites
 1. Java JDK 8
 2. [gradle](https://gradle.org/install/)

## Configuration
 1. You will probably need to edit these properties in `poshi-runner.properties` to suit your needs
    `test.base.dir.name` to where you have your test files (i.e `/path/to/local/poshiFiles`)
    `test.name` (i.e. `LocalFile.MyTest#<testName>` or  `Portal.PortalSmoke#Smoke` if using a resource jar)
    `browser.firefox.bin.file`  (if you need to specify where the binary is, i.e. `/opt/firefox45/firefox`)

** You can change the poshi-runner version here: https://gist.github.com/yichenroy/7673d0360c3564c744d40ac9cf892e77#file-standalone-poshi-gradle-L16
** Current version liferay-portal is using the latest poshi runner version, published here: https://repository.liferay.com/nexus/index.html#nexus-search;quick~com.liferay.poshi.runner
** For `chrome`, make sure these properties are set in `poshi-runner.properties`: https://gist.github.com/yichenroy/822f31006dc47d3fbc1fc7613d4b3ae9#gistcomment-3081469
** You can also see the list of properties here: https://github.com/liferay/liferay-portal/blob/master/modules/test/poshi/poshi-properties.markdown

## Using Poshi
 1. Run using the command `./gradlew -P<propertyValue> <task>`
    for Example `./gradlew -P<propertyValue> runPoshi`
    You can run `./gradlew help` to see the help message or `./gradlew tasks` to see available tasks (tasks should be under `Poshi tasks`)

 3. To run standalone poshi in conjunction with this properties file, you can use the command
    `gradlew -PposhiRunnerExtPropertyFileNames=poshi-runner.properties <task>`

** Currently there are no function files readily available for use with standalone poshi.