pipeline {
  agent any
  stages {
    stage('Deploy CloudHub') {
      environment {
        ANYPOINT_CREDENTIALS = credentials('ANYPOINT')
      }
      steps {
        bat 'mvn deploy -P cloudhub -Dmule.version=4.1.5 -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}'
      }
    }
  }
}