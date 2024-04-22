pipeline {
    agent any

    stages {
        stage('Check SonarQube Connection') {
            steps {
                script {
                    def serverUrl = 'http://sonarqube.example.com' // Replace with your SonarQube server URL
                    def serverVersion = ''
                    
                    try {
                        def sonar = new SonarQubeServerBuilder(serverUrl).build()
                        serverVersion = sonar.api.system.info().version
                        println "Connected to SonarQube version ${serverVersion}"
                    } catch (Exception e) {
                        println "Failed to connect to SonarQube server at ${serverUrl}: ${e.message}"
                        error("Connection to SonarQube failed")
                    }
                }
            }
        }
    }
}
