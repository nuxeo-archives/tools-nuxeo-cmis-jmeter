#    -*- mode: org -*-
#+TITLE: cmisbench JMeter

* Description

  This is a Nuxeo CMIS benchmark using JMeter script.

  The test scenario is the following:

  1. create a folder at the root level
  2. create 10 files
  3. perform a getChildren on the folder

  This senario can be repeated using the loop properties (see below).

* Requirement

  - JMeter 2.4
    wget http://archive.apache.org/dist/jakarta/jmeter/binaries/jakarta-jmeter-2.4.tgz

  - maven

  - ant

* Configuration
  
  Copy the build.properties.sample into build.properties and edit:

  - jmeter.home :: full path to the jmeter home

  - username, password, base_url :: access to the CMIS server

  - size_kb :: average size in KB of the content of created document

  - threads :: number of concurrent threads

  - loop :: number of time the scenario is repeated

  - rampup :: Ramp-Up period in seconds

* Building and deploying

  Make sure you are allowed to write into the $JMETER_HOME/lib/junit folder then:

  ant deploy

* Running the bench with ant

  ant run

  This produce a basic html report.

* Running the bench with the JMeter GUI
  
  Load the ./loadtests/cmis-bench.xml file.
  Check the Parameters user defined variables.

* Running the junit test with maven

  This will use the default properties hard coded in the junit test.

  mvn test

* To do
** TODO Add a delete action
** TODO Render the throughput in the report
   
