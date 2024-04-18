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
    stages {
        stage('Compile') {
            steps {
                sh '/usr/lib/jvm/java-17-openjdk-amd64/bin/javac hello.java'
                sh 'java hello'
            }
        }
    }
}

