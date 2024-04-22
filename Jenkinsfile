pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your version control system
                git 'https://github.com/your/repository.git'
            }
        }
        stage('Build') {
            steps {
                // Build your project (e.g., compile code)
                sh 'mvn clean package' // Assuming Maven is your build tool
            }
        }
        stage('SonarQube Analysis') {
            environment {
                // Define SonarQube server configuration
                SONAR_HOST_URL = 'http://sonarqube.example.com'
                SONAR_TOKEN = credentials('sonarqube-token') // Use Jenkins credentials plugin to store the token
            }
            steps {
                // Run SonarQube analysis
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
