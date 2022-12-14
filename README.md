# Notes - Flutter with Sqlite database and SonarQube 
 This is a note taking app made with flutter.<br>
## Concepts used:
<ul>
<li>Sqlite database to store custom Note object.</li>
<li>Search Functionality</li>
<li>Staggered GridView</li>
</ul>

## Sonar Server Configuration: (For Windowns, Check offical document for the othre OS)

#Step1
1. Download and install Java 11 on your system. 
2. Download the SonarQube Community Edition zip file
3. Download the SonarScanners (Code Analyzer)
4. **Download the Flutter Plug-In (For Flutter Only)**

#Step2
Set Environment Path:
1. JDK ==> ..\SonarLocal\jdk-11.0.17+8\bin
2. Sonarqube ==> ..\SonarLocal\sonarqube-8.9.10.61524\bin\windows-x86-64
3. Sonarscanner ==> ..\SonarLocal\sonar-scanner-4.7.0.2747-windows\bin

#Step3
1. Open wrapper.conf ==> (File Path ..\SonarLocal\sonarqube-8.9.10.61524\conf\)
2. Update wrapper.java.command=../SonarLocal/jdk-11.0.17+8/bin/java

#Step4 (This is very important)
1. Open command line 
2. CD ..\SonarLocal\sonarqube-8.9.10.61524\bin\windows-x86-64
3. Type ==> startsonar
4. Hit http://localhost:9000/ or your server URL where you setup sonar

## Flutter Configuration

1. Move Plug-In Jar file at  
..\SonarLocal\sonarqube-8.9.10.61524\lib\extensions

2. create sonar.properties file at root level of project and write below script  

3. Sonar Script
sonar.projectKey=<PROJECT-KEY>
sonar.projectName=<PROJECT-NAME>
sonar.projectVersion=1.0
sonar.host.url = http://localhost:9000/ // Default or your server URL
sonar.scm.disabled=true
sonar.sources=lib
sonar.login=<TOKEN>
sonar.sourceEncoding=UTF-8

4. Type below command one after other
flutter clean 
flutter pub get
sonar-scanner

Thank you!
