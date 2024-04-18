pipeline {
    agent any
    tools {
        // Define the JDK tool with the desired name and installation path
        jdk 'OpenJDK 17'
    }
    stages {
        stage('version') {
            steps {
                // Execute a shell command to get the version
                sh 'java -version'
            }
        }
        stage('hello') {
            steps {
                script {
                    def javaHome = tool 'OpenJDK 17'
                    sh "${javaHome}/bin/javac hello.java"
                }
            }
        }
    }
}

