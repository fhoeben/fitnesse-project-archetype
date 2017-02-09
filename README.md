# FitNesse using hsac-fitnesse-fixtures project archetype
[![Maven Central](https://img.shields.io/maven-central/v/nl.hsac/fitnesse-project.svg?maxAge=86400)](https://mvnrepository.com/artifact/nl.hsac/fitnesse-project)

This project contains the code to create a Maven archetype that can be used to generate a [FitNesse](http://fitnesse.org) 
project based on [hsac-fitnesse-fixtures](https://github.com/fhoeben/hsac-fitnesse-fixtures).

Based on this archetype one can create a new Maven project to contain a FitNesse installation/testSuite.
The archetype will create the boilerplate so the use can focus on writing their tests.

## Usage

To use the archetype from the command line:

 * Go to the directory under which you want to create the project.
 * Have the archetype create the project: `mvn archetype:generate -DarchetypeGroupId=nl.hsac -DarchetypeArtifactId=fitnesse-project`
 * Maven will prompt you for:
   * `groupId`: value of `groupId` element in the generated project's `pom.xml`.
   * `artifactId`: value of `artifactId` element in the generated project's `pom.xml`, and the name of the directory the project is created in.
   * `version`: value of `version` element in the generated project's `pom.xml`.
   * `package`: which java package (i.e. namespace) to use for the unit test to run tests on build server, or debug fixtures.
* Confirm the values you supplied by pressing 'enter', or entering `Y`.

The archetype will create a directory named after the 'artifactId' you supplied, which will contain the generated project.

To start using the project go to the directory created and enter `mvn clean compile exec:exec`, this will start the FitNesse
wiki at [http://localhost:9090/](http://localhost:9090/).
