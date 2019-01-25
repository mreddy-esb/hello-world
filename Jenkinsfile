pipeline{
 agent any
 environment {
    ANYPOINT = credentials('anypoint-credentials')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'maven'){
 				bat 'mvn clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'maven'){
 				bat 'mvn -f package deploy  -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Dsandbox -DmuleDeploy'
 			}
 		}
 	}
 }

}