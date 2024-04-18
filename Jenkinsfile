pipeline {
    agent any
    tools {
        // Define the JDK tool with the desired name and installation path
        jdk 'Oracle JDK'
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
                    def javaHome = tool 'Oracle JDK'
                    sh "${javaHome}/bin/javac hello.java"
                }
            }
        }
    }
}

