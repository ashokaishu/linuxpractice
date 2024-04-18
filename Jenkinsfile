pipeline {
    agent any
    stages {
        stage('version') {
            steps {
                // Execute a shell command to get the version
                sh 'java -version'
            }
        }
        stage('hello') {
            steps {
                sh 'javac hello.java'
                sh 'java hello'
            }
        }
    }
}

