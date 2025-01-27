before presentation
- close all iterm windows
- use ./serve.sh for presentation

---------------
presentation
---------------
#slide 1
* welcome to my talk about gradle in the developer ecosystem

* my name is
** working as
** believe in software development as a craftsmanship

#slide 2

* craftsmen need tools, we need tools
	
#slide 3

* What we want to look at

---------------

#DEMOS

## idea 13 Demo (prerecorded)

## Netbeans Demo (prerecord) (record done)
(clean gradle cache before)

* import spring-integration (fast)
* open spring-integration-twitter
* show "empty" dependencies
* explain context menu
* run build
	* show dependencies
* run (single) test
* change dependency (log4j -> 1.2.17)
* run single test again
* show changed dependency libs in testCompile
* show sample main file
* run main file
* debug main file
* not syntax support

## STS DEMO (prerecord)  (record done)

* open STS
* import GRADLE project from /Users/Rene/gradleware/github/breskeby/private-gradle-talks/2013/gradle-summit/dev-ecosystem/repos/spring-integration


* selected projects
	- spring-integration
	- spring-integration-twitter
	- spring-integration-http
	- spring-integration-scripting
	- spring-integration-security
	
* run some tests via IDE
* run some tests via Gradle
* change log4jVersion = '1.2.12' > '1.2.17'
* change sorting of #gradle dependencies in spring-integration-core'
* add 'build.gradle' file to spring-integration-twitter:

    sourceSets{
	    integTest
    }

* refresh sources

* create custom task

    task sayHello << {
        println "hello"
    }

* open source at https://github.com/SpringSource/eclipse-integration-gradle
* more info at https://github.com/SpringSource/eclipse-integration-gradle/wiki


## Jenkins Demo

* show plugin in plugin listing
* show general gradle plugin configuration
	* create gradle-1.5 in plugin configuration
	* create gradle-1.6 in plugin configuration
	
* create job from scratch
	* git url: file:///Users/Rene/gradleware/github/breskeby/private-gradle-talks/2013/gradle-summit/dev-ecosystem/samples/multiparallel
	* gradle switch -i
	* gradle tasks build
 
* run job
* show console
* detecting the output of a given task

// https://wiki.jenkins-ci.org/display/JENKINS/Gradle+Plugin
//
// Using the Gradle API for accessing all the Gradle functionalities
// Providing a Maven-like or Ivy-like integration
// 		Multi-project detection
// 		Adding automatic tests result path detection
// 		Listing executed tasks with time execution for each task
// 		Providing a log for each module in a multi-project

# bamboo demo

* show addon overview (artifactory gradle plugin)
* create sample build
MyProject -> Basic Coverage -> macosx 1.7
* show gradle options
* configure test parser
	'**/test-results/*.xml'
* run build

# teamcity demo
* bundled plugin shipped with teamcity 
* console support

# GO - Screenshot

# drone.io demo
	-> clear all projects
	-> show drone.io
	-> vorteil:
		- gute ui
		- support for bitbucket, github, goodle-code
	* login via github
	* select sampleproject
	* configure via wrapper

	# Sonar
	* zoom screen
	* show nemo (http://nemo.sonarsource.org)
		* mention plugins (C++, Erlang, PL/SQL)
		* eclipse plugins
	* show Active-MQ
	* show history graph in dashboard
	* open petclinic sample
	* configure sonar

	    //sonarRunner {
	    //    sonarProperties {
	    //        property "sonar.host.url", "http://localhost:9000"
	    //        property "sonar.jdbc.url", "jdbc:h2:tcp://localhost:9092/sonar"
	    //        property "sonar.jdbc.driverClassName", "org.hibernate.dialect.H2Dialect"
	    //        property "sonar.jdbc.username", "sonar"
	    //        property "sonar.jdbc.password", "sonar"
	    //    }
	    //}

* gradlew tasks
* "gradlew sonarRunner"
* show console
* show localhost:9000
* enable jacoco
* "gradlew check sonarRunner"

#TODO

## jrebel

###DEMO
---
remove zeroturnaround plugin from cache
---
> mate . (in petclinic)
> show build.gradle
--> apply zeroturnaround plugin
> gradlew tasks
> gradlew generateRebel
> gradlew jettyRun
	 -> monitoring
	 -> show available plugins
	
> open localhost:9123/petclinic

--> open idea
--> fix welcome message (messages.properties)
--> gradle classes
--> reload petclinic in browser
--> create owner (Rene, G. / at the hyatt / santa clara)

> change 
-> use petclinic

-- build.gradle --

------------------

## deployment
## bintray
## liverebel
## vagrant

#credits
* jungle.jpg (http://www.flickr.com/photos/geographyalltheway_photos/4168656319)
* jungle_path (http://www.flickr.com/photos/iamagenious/396268675)
* tools_bw (http://www.flickr.com/photos/zzpza/3269784239/)
* spring team for their sample project
* http://creativecommons.org/licenses/by/3.0/