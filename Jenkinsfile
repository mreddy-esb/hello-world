pipeline{
 agent any
 environment {
    ANYPOINT = credentials('anypoint-credentials')
 }
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f mule-jenkins-pipeline/pom.xml package deploy  -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Dsandbox -DmuleDeploy'
 			}
 		}
 	}
 }

}