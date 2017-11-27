# Apache-Spark

## Installing Apache Spark on Mac
To successfully install Apache Spark on Mac, there are three requirements:
  1. *Java* (**Note: JDK-9 is currently not stable with Apache Spark-2.2.0 **)
  2. *Scala* 
  3. *Apache Spark*
  
  1. *Java*
    For Mac, the following will reference and install Java 9. However, as mentioned above, this version of Java is not currently stable with Apache Spark. 
     ```bash 
     brew cask install java
     ```
     The correct Java 8 JDK can be downloaded from [here.](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
     
  2. *Scala*
    Once the Java 8 JDK is installed, install Scala. The following will install Scala from the homebrew 
    ```bash
    brew install scala
    ```
    
   3. *Apache Spark*
   Finally, once both *Java* and *Scala* have been installed, Apache Spark can be installed, again using homebrew. This can be installed with:
   ```bash
   brew install apache-spark
   ```
## File location
If installed from 'brew' Apache Spark will be installed to:

```bash
/usr/local/Cellar/apache-spark/
```
   
   
## Errors
  Below is an error which arose from the Java 9 JDK being installed (which is currently unstable with Apache Spark-2.2.0)
  
  ```bash
  Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).

Failed to initialize compiler: object java.lang.Object in compiler mirror not found.
** Note that as of 2.8 scala does not assume use of the java classpath.
** For the old behavior pass -usejavacp to scala, or if using a Settings
** object programmatically, settings.usejavacp.value = true.

Failed to initialize compiler: object java.lang.Object in compiler mirror not found.
** Note that as of 2.8 scala does not assume use of the java classpath.
** For the old behavior pass -usejavacp to scala, or if using a Settings
** object programmatically, settings.usejavacp.value = true.
Exception in thread "main" java.lang.NullPointerException
```
*Solution*
1. Install the Java 8 JDK from [here.](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
2. In terminal, run ``` 
/usr/libexec/java_home -V
        ``` to identify the Java Virtual Machines on your Mac
3. Run ```bash export JAVA_HOME=`/usr/libexec/java_home -v 1.8` ```. This will set the default Java Virtual Machine to Java 8. 

