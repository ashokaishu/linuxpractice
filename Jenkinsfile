pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your Git repository
                git 'https://github.com/ashokaishu/linuxpractice.git'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                // Run SonarQube analysis
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar' // Assuming Maven is your build tool
                }
            }
        }
        stage('Quality Gate') {
            steps {
                // Wait for SonarQube analysis to complete and check the Quality Gate
                timeout(time: 1, unit: 'HOURS') {
                    // Wait for the analysis to be completed and retrieve the Quality Gate status
                    waitForQualityGate abortPipeline: true // Set abortPipeline parameter to true
                }
            }
        }
    }
}
