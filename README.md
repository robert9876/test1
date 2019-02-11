Repository to show problem with maven-install-plugin.

when you call
````
  mvn clean install
````

you get:
````
[INFO] --- maven-install-plugin:2.5.2:install-file (install-small-file) @ test1 ---
[INFO] Installing D:\Workarea\sample\test1\target\blabla.jar to C:\Users\xxx\.m2\repository\test1\blabla\1.0-SNAPSHOT\blabla-1.0-SNAPSHOT.jar
[INFO]
[INFO] --- maven-install-plugin:2.5.2:install-file (install-fat-file) @ test1 ---
[INFO] Installing D:\Workarea\sample\test1\target\blabla-jar-with-dependencies.jar to C:\Users\xxx\.m2\repository\test1\blabla\1.0-SNAPSHOT\blabla-1.0-SNAPSHOT-jar-with-dependencies.jar
````

When you uncomment
````
<!--
		<maven-install-plugin-version>3.0.0-M1</maven-install-plugin-version>
		<maven-deploy-plugin-version>3.0.0-M1</maven-deploy-plugin-version>
-->
````
in pom.xml, you will get:
````
[INFO] --- maven-install-plugin:3.0.0-M1:install-file (install-small-file) @ test1 ---
[INFO] Installing D:\Workarea\sample\test1\target\blabla.jar to C:\Users\xxx\.m2\repository\test1\blabla\1.0-SNAPSHOT\blabla-1.0-SNAPSHOT.jar
[INFO] Installing C:\Users\xxx\AppData\Local\Temp\blabla785845612597058907.pom to C:\Users\xxx\.m2\repository\test1\blabla\1.0-SNAPSHOT\blabla-1.0-SNAPSHOT.pom
[INFO]
[INFO] --- maven-install-plugin:3.0.0-M1:install-file (install-fat-file) @ test1 ---
[INFO] Installing C:\Users\xxx\AppData\Local\Temp\blabla-jar-with-dependencies9075916663990068550.pom to C:\Users\xxx\.m2\repository\test1\blabla\1.0-SNAPSHOT\blabla-1.0-SNAPSHOT.pom
[INFO] Installing D:\Workarea\sample\test1\target\blabla-jar-with-dependencies.jar to C:\Users\xxx\.m2\repository\test1\blabla\1.0-SNAPSHOT\blabla-1.0-SNAPSHOT-jar-with-dependencies.jar
````

(see https://issues.apache.org/jira/browse/MINSTALL-156?filter=-2 for details)
