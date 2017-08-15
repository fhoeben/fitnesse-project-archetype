# FitNesse using hsac-fitnesse-fixtures project archetype
[![Maven Central](https://img.shields.io/maven-central/v/nl.hsac/fitnesse-project.svg?maxAge=86400)](https://mvnrepository.com/artifact/nl.hsac/fitnesse-project)

This project contains the code to create a Maven archetype that can be used to generate a [FitNesse](http://fitnesse.org) 
project based on [hsac-fitnesse-fixtures](https://github.com/fhoeben/hsac-fitnesse-fixtures).

Based on this archetype one can create a new Maven project to contain a FitNesse installation/testSuite.
The archetype will create the boilerplate so the use can focus on writing their tests.

## Usage

To use the archetype from the command line:

 * Go to the directory under which you want to create the project.
 * (Maven should find the latest version of the archetype automatically, but it doesn't always.) Check the latest version number on the [releases page](https://github.com/fhoeben/fitnesse-project-archetype/releases/latest), and use this instead of `<latest-version>` in the next command.
 * Have the archetype create the project: `mvn archetype:generate -DarchetypeGroupId=nl.hsac -DarchetypeArtifactId=fitnesse-project -DarchetypeVersion=<latest-version>`
 * Maven will prompt you for:
   * `groupId`: value of `groupId` element in the generated project's `pom.xml`.
   * `artifactId`: value of `artifactId` element in the generated project's `pom.xml`, and the name of the directory the project is created in.
   * `package`: which java package (i.e. namespace) to use for the unit test to run tests on build server, or debug fixtures.
   * `testSuiteName`: name for the (boilerplate) test suite to create, where you can define your own tests immediately. (Must be a valid [wiki-word](http://fitnesse.org/FitNesse.FullReferenceGuide.UserGuide.FitNesseWiki.WikiWord).)
* Confirm the values you supplied by pressing 'enter', or entering `Y`.

The archetype will create a directory named after the 'artifactId' you supplied, which will contain the generated project.

## Getting Started with the Generated Project

To start using the project go to the directory created and enter `mvn clean compile exec:exec`, this will start the FitNesse
wiki at [http://localhost:9090/](http://localhost:9090/). If you append 'testSuiteName' (i.e. the value you supplied when 
prompted by Maven for that property during archetype creation) to the URL you'll go straight to 
the suite where you can start defining your own tests.

A more detailed description on how to set up a development environment to work on a project generated from this archetype
(i.e. [sample-fitnesse-project](https://github.com/fhoeben/sample-fitnesse-project)) can be found in the
[hsac-fitnesse-fixtures' wiki](https://github.com/fhoeben/hsac-fitnesse-fixtures/wiki/Installation-guide).