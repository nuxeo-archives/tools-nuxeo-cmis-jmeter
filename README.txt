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
  
  Edit the build.properties file

  - jmeter.home :: full path to the jmeter home, the $JMETER_HOME/lib/junit
		   must be writable.

  - username, password, base_url :: access to the CMIS server

  - threads :: number of concurrent threads

  - loop :: number of time the scenario is repeated

  - rampup :: Ramp-Up period in seconds

* Building and deploying

  mvn -Dmaven.test.skip.exec=true clean package dependency:copy-dependencies
  ant deploy

* Running the bench with ant

  ant run

  This produce a basic html report.

* Running the bench with JMeter GUI
  
  Load the ./loadtests/cmis-bench.xml file.
  Check the Parameters user defined variables.

* Running the junit test with maven

  mvn test


* To do
** DONE Add a rampup period
   CLOSED: [2011-08-26 ven. 10:51]
   :LOGBOOK:
   - State "DONE"       from "TODO"       [2011-08-26 ven. 10:51]
   :END:
** TODO Remove debug trace
   and add log4j conf
** TODO Add a file content and title
** TODO Render the throughput in the report
** TODO Run build from ant
   include the mvn cmd in ant build
