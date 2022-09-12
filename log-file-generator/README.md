# Log File Generator

## Setup

1. Java - On macOS, you can install Java using Homebrew (`brew install java`)

2. JDK - Download the latest JDK from https://www.oracle.com/java/technologies/downloads/

3. Maven - Install maven by following the guide on https://maven.apache.org/install.html

## Folder structure

```
.
├── output/
│   └── logs/ (log4j places the generated log files within this folder)
├── res/ (contains sample text data that's used to make the log file)
├── src/
│   ├── main/
│   │   ├── java/com/fa22/cs425/mp1/grp65/log-file-generator/ (App code folder)
│   │   └── resources/ (log4j2 config goes here)
│   └── test/ (unit tests should go here)
├── target/ (this is the build folder, contains the target JAR file of the application)
│   └── dependency/ (contains jar dependencies that are needed to run the application)
└── pom.xml (manifest/configuration of the maven project)
```

## Building the project

See https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html for more detailed instructions


## TL;DR
Execute the following steps in sequence for a new, clean build
```
mvn clean
mvn install
mvn dependency:copy-dependencies
mvn package
```

And finally to run the Jar, execute
```
java -cp "target/log-file-generator-1.0-SNAPSHOT.jar:target/dependency/*" com.cs425.mp1.logfilegenerator.App
```

### Create workspace

To create the workspace, run `mvn archetype:generate -DgroupId=com.<id> -DartifactId=<artifact-name> -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false` 

### Install

To install the required dependencies, run `mvn install`

To copy the dependencies to the target folder for running the application, run `mvn dependency:copy-dependencies` 

### Clean

To clean workspace, run `mvn clean`

`mvn clean install -U ` runs a clean build

### Build

Finally, to compile, build, execute tests and generate the Jar file, run `mvn package`

### Run

The jar can be directly executed by running `java -cp "target/log-file-generator-1.0-SNAPSHOT.jar:target/dependency/*" com.cs425.mp1.logfilegenerator.App`