
pipeline {
    agent any
    tools{
        maven 'M2_HOME'
    }

    stages {

        stage("Analysis by SonarQube"){
            steps {
                withSonarQubeEnv('sonarQube'){
                    sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=roberttemta_airport_Geolocation_Project'
                }
            }
        }
    }
}