#+TITLE: cmis-bench readme

* Introduction

  This is a Nuxeo CMIS bench using JMeter script.

  The scenario test scenario is the following:

  1. create a folder at the root level
  2. create 10 files
  3. perform a getChildren on the folder

  This senario can be repeated using the loop properties (see below).

* Requirement

  - JMeter 2.4
  - maven
  - ant

* Configuration
  
  Edit the build.properties file and set the 
  - jmeter.home :: full path to the jmeter home, the $JMETER_HOME/lib/junit
		   must be writable

  - username, password, base_url :: access to the CMIS server

  - threads :: number of concurrent threads

  - loop :: number of time the scenario is repeated

* Building

  mvn clean package dependency:copy-dependencies
  
* Installing

  ant deploy

* Running the bench with ant

  ant run

  This produce a basic html report.

* Running the bench with JMeter GUI
  
  load the ./loadtests/cmis-bench.xml file.
