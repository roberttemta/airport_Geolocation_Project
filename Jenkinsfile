/*
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
        
        stage('Checkout') {
            steps {
                git 'https://github.com/roberttemta/airport_Geolocation_Project.git'
            }
        }     
        stage('mvn Clean') {
            steps {
                sh 'mvn clean'
            }
        }stage('mvn Install') {
            steps {
                sh 'mvn install'
            }
        }
        stage('mvn Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
*/

pipeline {
    agent any

    tools {
        maven 'M2_HOME' // Ensure this is configured correctly in Jenkins under Global Tool Configuration
    }   
    
    stages {
        // SonarQube Analysis (Uncomment if needed)
        /*
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarQube') {
                    sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=roberttemta_airport_Geolocation_Project'
                }
            }
        }
        */

        stage('Checkout') {
            steps {
                git 'https://github.com/roberttemta/airport_Geolocation_Project.git'
            }
        }

        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Install') {
            steps {
                sh 'mvn install'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
