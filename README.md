[![Build Status](https://travis-ci.org/iluwatar/uml-reverse-mapper.svg?branch=master)](https://travis-ci.org/iluwatar/uml-reverse-mapper)[![Coverage Status](https://coveralls.io/repos/iluwatar/uml-reverse-mapper/badge.svg?branch=master&service=github)](https://coveralls.io/github/iluwatar/uml-reverse-mapper?branch=master)

UML Reverse Mapper
===========================

Automatically generate [Graphviz](http://www.graphviz.org/) based class diagram from your code.

Using reflection, UML Reverse Mapper scans your packages that contain your code. It then builds a graph of class relations and outputs a Graphviz .dot file.

### Using from the command-line

Build the `urm-core` project with `mvn clean package` and grab the generated artifact `urm-core-1.0-SNAPSHOT.jar`. Then you need the archive that will be analyzed. In this example we use `abstract-factory-1.6.0.jar` and assume the package name to be `com.iluwatar.abstractfactory`. Place the jar-files in the same directory and execute the following command.

    java -cp abstract-factory-1.6.0.jar:urm-core-1.0-SNAPSHOT.jar com.iluwatar.DomainMapperCli -p com.iluwatar.abstractfactory

This will scan all classes under the package `com.iluwatar.abstractfactory` and output the .dot file to your console output. If you want to write it to file use switch `-f filename.dot`. If you need to scan multiple packages use format `-p "com.package1, com.package2"`. Note that under Windows OS the classpath separator is `;` instead of `:`;
