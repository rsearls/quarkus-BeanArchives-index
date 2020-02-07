# quarkus-BeanArchives-index


Deploying the app results is the following error message and none of
the test methods being called. I have traced the error into io.quarkus.arc.processor.BeanArchives
but have been unsuccessful determining root cause.

    [INFO] Running org.jboss.resteasy.test.asynch.AsyncInjectionTest
    18:07:48,889 INFO  [org.jbo.threads] JBoss Threads version 3.0.0.Final
    18:07:49,150 WARN  [io.qua.arc.pro.BeanArchives] Failed to index boolean: Stream closed
    18:07:49,153 WARN  [io.qua.arc.pro.BeanArchives] Failed to index char: Stream closed
    18:07:49,154 WARN  [io.qua.arc.pro.BeanArchives] Failed to index byte: Stream closed
    18:07:49,155 WARN  [io.qua.arc.pro.BeanArchives] Failed to index short: Stream closed
    18:07:49,157 WARN  [io.qua.arc.pro.BeanArchives] Failed to index int: Stream closed
    18:07:49,158 WARN  [io.qua.arc.pro.BeanArchives] Failed to index long: Stream closed
    18:07:49,159 WARN  [io.qua.arc.pro.BeanArchives] Failed to index float: Stream closed
    18:07:49,160 WARN  [io.qua.arc.pro.BeanArchives] Failed to index double: Stream closed
    [INFO] Tests run: 0, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 3.106 s - in org.jboss.resteasy.test.asynch.AsyncInjectionTest




Before running the test install this archive in your local repo.
Here is the cmd to do it.

mvn install:install-file \
   -Dfile=___FIX_THIS___/lib/utils-arquillian-utils-4.5.0-SNAPSHOT.jar \
   -DgroupId=org.jboss.resteasy \
   -DartifactId=utils-arquillian-utils \
   -Dversion=4.5.0-SNAPSHOT \
   -Dpackaging=jar 

Execution env.
    jdk 11.0.2
    mvn 3.6.0
    quarkus 1.2.0.Final
    
  The pom.xml file contains the minimum archives required to compile and run the tests.
  
  Test file org.jboss.resteasy.test.asynch.AsyncInjectionTest
  demonstrates the issue.  See pom.xml line 307
