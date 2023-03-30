# An introduction to Build Tools (Maven, Gradle and NPM)

This repository contains a short introduction to Build Tools.

## Maven
Maven was created by Jason van Zyl and is a build tool for Java projects. It is based on the concept of a project object model (POM). The POM is an XML file that contains information about the project and configuration details used by Maven to build the project. The POM is the fundamental unit of work in Maven. It is a central piece of information that is used to coordinate builds, reporting and documentation from a central piece of information.

### Installation
To install Maven, you can download it from the [Maven website](https://maven.apache.org/download.cgi). You can also install it using a package manager like [Homebrew](https://brew.sh/) on macOS or [Chocolatey](https://chocolatey.org/) on Windows.
To test if Maven is installed correctly, run `mvn -v` in your terminal. You should see something like this:
```
Apache Maven 3.8.1 (05c21c65bdfed0f71a2f2ada8b84da59348c4c5d)
Maven home: /Users/john/programs/maven
Java version: 17.0.4.1, vendor: Eclipse Adoptium, runtime: /Library/Java/JavaVirtualMachines/temurin-17.jdk/Contents/Home
Default locale: en_RO, platform encoding: UTF-8
OS name: "mac os x", version: "12.3", arch: "aarch64", family: "mac"
```

### Maven Wrapper
The Maven Wrapper is a tool that allows you to use Maven without installing it. The Maven Wrapper is a set of scripts that will download Maven and use it to run your Maven commands. The Maven Wrapper is useful when you want to use Maven on a machine that does not have Maven installed. The Maven Wrapper is also useful when you want to use a specific version of Maven for your project. 
The Maven Wrapper will live in the `mvnw` and `mvnw.cmd` files. The `mvnw` file is for Unix-based systems and the `mvnw.cmd` file is for Windows-based systems. There is also a `.mvn` directory that contains the `wrapper` directory. The `wrapper` directory contains the `maven-wrapper.jar` file and the `maven-wrapper.properties` file. The `maven-wrapper.jar` file is the Maven Wrapper JAR file and the `maven-wrapper.properties` file is the Maven Wrapper properties file. The Maven Wrapper properties file contains the Maven version that will be used by the Maven Wrapper. The Maven Wrapper properties file will have the following content:
```
distributionUrl=https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.8.1/apache-maven-3.8.1-bin.zip
```

### Creating a Maven project
To create a Maven project, you can use the [Maven Archetype Plugin](https://maven.apache.org/archetype/maven-archetype-plugin/). The plugin is used to generate a project from an archetype (a project template). To create a Maven project, run the following command in your terminal:
```
mvn archetype:generate -DgroupId=com.example -DartifactId=hello-world -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
This command will create a Maven project in the `hello-world` directory. The project will have the following structure:
```
hello-world
├── .mvn
│   └── wrapper
│       ├── MavenWrapperDownloader.java
│       ├── maven-wrapper.jar
│       └── maven-wrapper.properties
├── pom.xml
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── App.java
    │   └── resources
    └── test
        ├── java
        │   └── com
        │       └── example
        │           └── AppTest.java
        └── resources
```
The `pom.xml` file is the project object model and is the only mandatory file in a Maven project. The `src` directory contains the source code and resources of the project. The `main` directory contains the source code and resources of the main part of the project. The `test` directory contains the source code and resources of the tests of the project.

### Building a Maven project
To build a Maven project, run the following command in your terminal:
```
mvn package
```
This command will compile the source code of the project and package it in its distributable format, such as a JAR file. The JAR file will be located in the `target` directory. The `target` directory will have the following structure:
```
target
├── classes
│   └── com
│       └── example
│           └── App.class
├── generated-sources
│   └── annotations
├── generated-test-sources
│   └── test-annotations
├── hello-world-1.0-SNAPSHOT.jar
├── maven-archiver
│   └── pom.properties
├── maven-status
│   └── maven-compiler-plugin
│       ├── compile
│       │   └── default-compile
│       │       ├── createdFiles.lst
│       │       └── inputFiles.lst
│       └── testCompile
│           └── default-testCompile
│               ├── createdFiles.lst
│               └── inputFiles.lst
├── surefire-reports
│   └── com.example.AppTest.txt
└── test-classes
    └── com
        └── example
            └── AppTest.class
```
The `classes` directory contains the compiled classes of the project. The `test-classes` directory contains the compiled classes of the tests of the project. The `hello-world-1.0-SNAPSHOT.jar` file is the distributable file of the project. The `surefire-reports` directory contains the test reports of the project.

### Running a Maven project
To run a Maven project, run the following command in your terminal:
```
mvn exec:java -Dexec.mainClass="com.example.App"
```
This command will run the `main` method of the `App` class. The `App` class is located in the `com.example` package and is in the `src/main/java/com/example/App.java` file. The `App` class will have the following content:
```java
package com.example;

public class App {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```
The `main` method will print `Hello World!` in the terminal.


## Gradle
Gradle was created by Gradle, Inc. and is a build tool for Java projects. It is based on the concept of a build script. The build script is a Groovy or Kotlin file that contains information about the project and configuration details used by Gradle to build the project. The build script is the fundamental unit of work in Gradle. It is a central piece of information that is used to coordinate builds, reporting and documentation from a central piece of information.

### Installation
To install Gradle, you can download it from the [Gradle website](https://gradle.org/releases/). You can also install it using a package manager like [Homebrew](https://brew.sh/) on macOS or [Chocolatey](https://chocolatey.org/) on Windows.
To test if Gradle is installed correctly, run `gradle -version` in your terminal. You should see something like this:
```
------------------------------------------------------------
Gradle 7.6
------------------------------------------------------------

Build time:   2022-11-25 13:35:10 UTC
Revision:     daece9dbc5b79370cc8e4fd6fe4b2cd400e150a8

Kotlin:       1.7.10
Groovy:       3.0.13
Ant:          Apache Ant(TM) version 1.10.11 compiled on July 10 2021
JVM:          17.0.6 (Homebrew 17.0.6+0)
OS:           Mac OS X 12.3 aarch64
```

### Gradle Wrapper
The Gra

### Creating a new Gradle project
To create a Gradle project, run the following command in your terminal:
```
gradle init --type java-application
```
This command will create a Gradle project in the `hello-world` directory. The project will have the following structure:
```
hello-world
├── build.gradle
├── .gradle 📂
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
├── settings.gradle
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── App.java
    │   └── resources
    └── test
        ├── java
        │   └── com
        │       └── example
        │           └── AppTest.java
        └── resources
```
The `build.gradle` file is the build script of the project. The `settings.gradle` file is the settings script of the project. The `src` directory contains the source code and resources of the project. The `main` directory contains the source code and resources of the main part of the project. The `test` directory contains the source code and resources of the tests of the project.

### Building a Gradle project
To build a Gradle project, run the following command in your terminal:
```
gradle build
```
This command will compile the source code of the project and package it in its distributable format, such as a JAR file. The JAR file will be located in the `build/libs` directory. The `build/libs` directory will have the following structure:
```
build
├── classes
│   └── java
│       └── main
│           └── com
│               └── example
│                   └── App.class
├── generated
│   └── sources
│       └── annotationProcessor
│           └── java
│               └── main
├── libs
│   └── hello-world-1.0-SNAPSHOT.jar
├── reports 📂
├── resources
│   └── main
├── test-results
│   └── test
│       └── binary
│           └── output.bin
└── tmp
    └── compileJava
        └── source-classes-mapping.txt
```
The `classes` directory contains the compiled classes of the project. The `libs` directory contains the distributable file of the project. The `test-results` directory contains the test reports of the project.

### Running a Gradle project
To run a Gradle project, run the following command in your terminal:
```
gradle run
```
This command will run the `main` method of the `App` class. The `App` class is located in the `com.example` package and is in the `src/main/java/com/example/App.java` file. The `App` class will have the following content:
```java
package com.example;

public class App {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```
The `main` method will print `Hello World!` in the terminal.

## Npm  
npm is a package manager for JavaScript projects. It is the default package manager for the JavaScript runtime environment Node.js. It consists of a command line client, also called npm, and an online database of public and paid-for private packages, called the npm registry. The registry is accessed via the client, and the available packages can be browsed and searched via the npm website.

### Installation
To install npm, you can download it from the [npm website](https://www.npmjs.com/get-npm). You can also install it using a package manager like [Homebrew](https://brew.sh/) on macOS or [Chocolatey](https://chocolatey.org/) on Windows. 
To install Node and NPM using nvm, run the following command in your terminal:
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```
This command will install nvm. To test if nvm is installed correctly, run `nvm --version` in your terminal. You should see something like this:
```
0.39.0
```
To install Node and NPM using nvm, run the following command in your terminal:
```
nvm install 18
```
This command will install Node and NPM. To test if Node and NPM are installed correctly, run `node -v` and `npm -v` in your terminal. You should see something like this:
```
v18.0.0

8.0.0
```

### Creating a new npm project
To create a new npm project, create a new folder called `hello-world` run the following command in your terminal (inside the `hello-world` directory):
```
npm init -y
```
This command will create a new npm project in the `hello-world` directory. The project will have the following structure:
```
hello-world
├── package-lock.json
├── package.json
└── node_modules
```
The `package.json` file is the manifest of the project. The `package-lock.json` file is the lockfile of the project. The `node_modules` directory contains the dependencies of the project.

Create a new file called `index.js` in the `hello-world` directory. The `index.js` file will have the following content:
```js
console.log("Hello World!");
```

### Installing a dependency
To install a dependency, run the following command in your terminal:
```
npm install <dependency>
```

### Building a npm project
To build a npm project, run the following command in your terminal:
```
npm run build
```
This command will compile the source code of the project and package it in its distributable format, such as a JAR file. The JAR file will be located in the `dist` directory. 

### Running a npm project
To run a npm project, run the following command in your terminal:
```
npm run start
```
To create an executable Node project, add the following code to the `package.json` file:
```json
{
  ...
  "bin": {
    "hello-world": "index.js"
  },
  ...
}
```
Also, in the `index.js` file, add the following first line, also called a shebang:
```js
#!/usr/bin/env node

console.log("Hello World!");
```

To run the executable Node project, run the following command in your terminal:
```
npm link
```
This command will create a symbolic link to the `hello-world` executable. To test if the symbolic link is created correctly, run `hello-world` in your terminal. You should see something like this:
```
Hello World!
```

You can also run the executable Node project by running the following command in your terminal:
```
node index.js
```
Also, you can use `npx` to run the executable Node project by running the following command in your terminal:
```
npx hello-world
```
