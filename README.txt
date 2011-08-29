#    -*- mode: org -*-
#+TITLE: cmisbench JMeter

* Description

  This is a Nuxeo CMIS benchmark using JMeter script.

  The test scenario is the following:

  1. Creates a random folder at the root level
  2. Creates 10 file documents with random contents using a french
     corpus
  3. Performs a getChildren on the folder

  This senario is running in loop for the specified duration.

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

  - rampup :: Ramp-Up period in seconds, this tells JMeter how long
	      to take to launch the concurrent threads

  - duration :: total duration of the bench

  - loop :: number of time the scenario is repeated (not used by
	    default the duration mode is used)

* Building and deploying

  Make sure you are allowed to write into the $JMETER_HOME/lib/junit folder then:

  ant deploy

* Running the bench with ant

  ant run

  This produce a basic html report.

* Running the bench with the JMeter GUI
  
  Load the ./loadtests/cmis-bench.xml file.

  Edit the "Parameters user defined variables". For instnace the
  default value for ${__property(rampup,RAMPUP,4)} is 4.

* Running the junit test with maven

  This will use the default properties hard coded in the junit test.

  mvn test

* To do
** TODO Add a delete action
** TODO Render the throughput in the report
   
