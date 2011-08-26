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

  - jmeter.home :: full path to the jmeter home

  - username, password, base_url :: access to the CMIS server

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

** DONE Add a rampup period
   CLOSED: [2011-08-26 ven. 10:51]
   :LOGBOOK:
   - State "DONE"       from "TODO"       [2011-08-26 ven. 10:51]
   :END:
** DONE Run build from ant
   CLOSED: [2011-08-26 ven. 12:50]
   :LOGBOOK:
   - State "DONE"       from "TODO"       [2011-08-26 ven. 12:50]
   :END:
   include the mvn cmd in ant build
** DONE Remove debug trace
   CLOSED: [2011-08-26 ven. 12:51]
   :LOGBOOK:
   - State "DONE"       from "TODO"       [2011-08-26 ven. 12:51]
   :END:
** DONE Add a log4j conf
   CLOSED: [2011-08-26 ven. 13:22]
   :LOGBOOK:
   - State "DONE"       from "TODO"       [2011-08-26 ven. 13:22]
   :END:
** TODO Add a file content and title
** TODO Render the throughput in the report
