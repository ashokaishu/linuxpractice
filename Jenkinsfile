pipeline {
    agent any
    stages {
        stage('version') {
            steps {
                // Execute a shell command to get the Java version
                script {
                    try {
                        sh 'java -version'
                    } catch (Exception e) {
                        echo 'Error: Java not found or unable to determine version'
                    }
                }
            }
        }
        stage('compile') {
            steps {
                // Compile the Java program
                script {
                    try {
                        sh 'javac hello.java'
                    } catch (Exception e) {
                        echo 'Error: Compilation failed'
                        error 'Compilation failed'
                    }
                }
            }
        }
        stage('run') {
            steps {
                // Run the Java program
                script {
                    try {
                        sh 'java hello'
                    } catch (Exception e) {
                        echo 'Error: Execution failed'
                        error 'Execution failed'
                    }
                }
            }
        }
    }
}
