# SonarQube setup

## 1. Download SonarQube Community Edition

Recommend version [9.9 LTA](https://www.sonarsource.com/products/sonarqube/downloads/historical-downloads/)

## 2. Download SonarScanner CLI
Download from [here](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarscanner/)

## 3. Start SonarQube Server

3.1 Extract the zip file from step 1

3.2 Navigate to `bin` directory

3.3 Start the server
  - On Windows
    - Navigate to `bin\windows-x86-64`
    - Run `StartSonar.bat`
  - On Linux/Mac OS
    - Navigate to `bin\macosx-universal-64`
    - Run `./sonar.sh start`

*Note: Make sure JDK is Java 17*

Now you can access SonarQube dashboard at [http://localhost:9000](http://localhost:9000/projects/create)

## 4. Run the analysis

4.1 Create a new project on SonarQube dashboard

4.2 Navigate to the directory of the project and create a new file *sonar-project.properties* under the directory of your project
```
sonar.projectKey=<YourProjectKey>
sonar.projectName=<YourProjectName>
sonar.login=<YourToken>
sonar.projectVersion=1.0
sonar.sources=src
sonar.host.url=http://localhost:9000
sonar.java.binaries=build/classes/java/main
sonar.java.libraries=build/libs/*.jar
```
4.3 Run SonarScanner
```
sonar-scanner
```

## 5. View the results

Access the SonarQube dashboard to see the analysis results.