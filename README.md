
# Gradle build scripts to create TeamCity tools

### Maven 3.3 tool

[![Download](https://api.bintray.com/packages/rodm/teamcity-plugins-generic/maven3_3-tool/images/download.svg)](https://bintray.com/rodm/teamcity-plugins-generic/maven3_3-tool/_latestVersion)

The `maven3.3.gradle` build script downloads Apache Maven 3.3 and repacks it into a TeamCity tool for
deployment to the build agents. The tool can be used in a build configuration using the parameter
`teamcity.tool.maven3_3`.

Builds using Maven 3.3 may fail with the error below, to work around this problem add the following system
property to the build configuration: `system.maven.multiModuleProjectDirectory` set to `%teamcity.build.checkoutDir%`. 

    -Dmaven.multiModuleProjectDirectory system propery is not set. Check $M2_HOME environment variable and mvn script match.
 
To build the tool run:

    ./gradlew -b maven3.3.gradle clean build
    
To deploy the tool copy the file `maven3_3-tool.zip` in the `build/distributions` directory to the
TeamCity server's plugin directory. 

### FindBugs 3.0 tool

[![Download](https://api.bintray.com/packages/rodm/teamcity-plugins-generic/findbugs3_0-tool/images/download.svg)](https://bintray.com/rodm/teamcity-plugins-generic/findbugs3_0-tool/_latestVersion)

The `findbugs3.gradle` build script downloads FindBugs 3.0 and repacks it into a TeamCity tool. The tool
can be used in a build configuration using the parameter `teamcity.tool.findbugs3_0`.

To build the tool run:

    ./gradlew -b findbugs3.gradle clean build
    
To deploy the tool copy the file `findbugs3_0-tool.zip` in the `build/distributions` directory to the
TeamCity server's plugin directory. 

### PhantomJS 2.1 tool

[![Download](https://api.bintray.com/packages/rodm/teamcity-plugins-generic/phantomjs-tool/images/download.svg)](https://bintray.com/rodm/teamcity-plugins-generic/phantomjs-tool/_latestVersion)

The `phantomjs.gradle` build script downloads PhantomJS 2.1.1 for Windows, Linux and Mac OS X and repacks them into
a TeamCity tool. The tool can be used in a build configuration using the parameter `teamcity.tool.phantomjs`. The
phantomjs binaries are available under the tool directory in the following paths

    bin/linux-i686/phantomjs
    bin/linux-x86_64/phantomjs
    bin/macosx/phantomjs
    bin/windows/phantomjs.exe

To build the tool run:

    ./gradlew -b phantomjs.gradle clean build

To deploy the tool copy the file `phantomjs-tool.zip` in the `build/distributions` directory to the
TeamCity server's plugin directory.
