About EAtools
=============

This prototype software can be used to extract the UML models from the
[Sparx Enterprise Architect](http://www.sparxsystems.com/products/ea/index.html) UML diagramming tool via it's Java
API (`eaapi.jar`). Our goal with this was to be able to extract diagrams for inclusion in the
[Confluence Wiki](http://www.atlassian.com/software/confluence), and give the diagrams fixed, and logical file names.

A lightning talk about this work was given at the [JavaZone](www.javazone.no) conference in 2009. The slides from the talk are found here: [http://www.slideshare.net/pspilling/agile-documentation-with-confluence-and-ea](http://www.slideshare.net/pspilling/agile-documentation-with-confluence-and-ea).

We are not planning to maintain or do more development on this code, but anyone who finds the code useful is welcome to
do whatever they want with it. 

    *******************************************************************************
    * DISCLAIMER:
    *
    * The code is written as part of a Proof of Concept. This implies that the code
    * may not be up to production quality standards with regards to:
    * - structure
    * - naming
    * - documentation
    * - test coverage
    * - robustness
    * - etc.
    *******************************************************************************

How to build and run the generate-diagrams app
----------------------------------------------

### Prerequisites

* JDK 1.6 & Maven 2 installed
* [Sparx Enterprise Architect](http://www.sparxsystems.com/products/ea/index.html) installed. *Note: Sparx Enterprise
Architect only runs on Windows.*

### Installation

1. Install the Enterprise Architect API jar file, which can be found in the `Java API` directory in the EA
installation. The standard location for this is: `C:\Program Files\Sparx Systems\EA\Java API`. Do the following:

        $ cd <the directory where the eaapi.jar is located>
        $ mvn install:install-file -DgroupId=org.sparx -DartifactId=eaapi -Dversion=1.0.0 -Dpackaging=jar -Dfile=eaapi.jar

2. cd back to the directory with the EAtools project, and compile the :

        $ mvn clean install

3. Build the eatools.jar file:

        $ mvn package -Dmaven.test.skip=true -DmainClass=no.eatools.diagramgen.EaDiagramGenerator -DjarFileName=eatools

### Usage

Run the generate-diagrams app:

        $ java -jar eatools.jar

--
Ove Scheel and Per Spilling, nov-des 2008