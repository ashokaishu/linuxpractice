node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "/opt/sonar-scanner-4.6.2.2472-linux/bin/sonar-scanner"
    }
  }
}
