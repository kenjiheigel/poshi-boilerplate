# poshi-boilerplate
How to use this gradle script:

Requirement:

 1. gradle must be installed
 
 Steps to use `standalone-poshi.gradle`
 
1. Place standalone-poshi.gradle into any directory with 'gradlew'
    Alternatively, go to any directory (or create a new directory) and then run `gradle wrapper` in the terminal of that directory, then place standalone-poshi.gradle into that directory.
    You can change the poshi-runner version here
    https://gist.github.com/yichenroy/7673d0360c3564c744d40ac9cf892e77#file-standalone-poshi-gradle-L16
    Current version liferay-portal is using the latest poshi runner version, published here:
    https://repository.liferay.com/nexus/index.html#nexus-search;quick~com.liferay.poshi.runner
 2. Run using the command `./gradlew -b standalone-poshi.gradle -P<property=value> <task>`
    for Example `./gradlew -b standalone-poshi.gradle -P<property=value> runPoshi`
    You can run `./gradlew -b standalone-poshi.gradle help` to see the help message or `./gradlew -b standalone-poshi.gradle tasks` to see available tasks (custom tasks should be under `Other tasks`)
 3. You can download this property file to be used with the standalone poshi, place this file in the same directory as standalone-poshi.gradle
    This is the default configuration similar to what we use in liferay-portal https://gist.github.com/yichenroy/822f31006dc47d3fbc1fc7613d4b3ae9
    Notably, you will probably need to edit these properties to suit your needs
    `test.base.dir.name` (i.e `/opt/dev/projects/github/liferay-portal/portal-web/test`)
    `test.name` (i.e. `LocalFile.PortalSmoke#Smoke` or  `Portal.PortalSmoke#Smoke` if using a resource jar)
    `browser.firefox.bin.file`  (if you need to specify where the binary is, i.e. `/opt/firefox45/firefox`)
 4. To run standalone poshi in conjunction with this properties file, you can use the command
    `gradlew -b standalone-poshi.gradle -PposhiRunnerExtPropertyFileNames=poshi-runner.properties <task>` 

** You can rename `standalone-poshi.gradle` to `build.gradle` to avoid having to provide `-b standalone-poshi.gradle` in every command. 
** Currently there are no function/macro/path files readily available for use with standalone poshi. 
** For `chrome`, make sure these properties are set: https://gist.github.com/yichenroy/822f31006dc47d3fbc1fc7613d4b3ae9#gistcomment-3081469
