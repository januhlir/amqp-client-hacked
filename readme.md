Modified version 3.1.5+ from **amqp-client** Mercurial.

The only change to code is in Frame.java around line 116.
Here I check size of incoming frame, if is too big, too big to cause OutOfMemoryException, read 
only first 1000B of the data and log them (using standard Java logging) in String and hex formats.

Mavenized build. Previously Ant was needed, which called some Python scripts to generate Java code.
The generated Java code is included, so Python is not needed. Same for Ant. Maven should be all you need. 
If you want to use Maven to deploy to local Maven repository (like Nexus) the distributionManagement
section has to be modified to local settings.

TODO: I have just copied source over to new location, to Maven standard src/main/java.
Ugly solution, better would be add "src", as opposed to standard Maven location of "src/main/java", to pom.xml, compiler plugin.
 
Removed (gitignored): lib, bundlor (they contained some Jars) and others. Hopefuly this will to break the build.