pipeline {
  agent any
  stages {
    stage('Deploy CloudHub') {
      environment {
        ANYPOINT = credentials('ANYPOINT')
      }
      steps {
        bat 'mvn deploy -P cloudhub -Dmule.version=4.1.5 -Dusername=${ANYPOINT_USR} -Dpassword=${ANYPOINT_PSW}'
      }
    }
  }
}
