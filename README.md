Minimal example to reproduce issue with gretty groovy classloader on Tomcat 8.

This example reproduces the issue using Spring XML Configuration.  

For an example with Spring Boot, please see: https://github.com/kpage/gretty-groovy-classloader

Works: ./gradlew jettyRun

Fails with groovy ClassCastException: ./gradlew tomcatRun

It seems that the ClassCastException is caused by the gretty plugin modifying 
the groovy classes that are loaded for the web app.  Building a WAR and manually 
deploying to Tomcat works fine.
