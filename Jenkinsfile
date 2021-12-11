pipeline {
	agent any

	stages{
		stage('Clone'){
			Steps{
		sh "rm -rf"
		sh "git clone https://github.com/steevCpp/my-jenkins-file"
	}
	stage('build'){
		sh 'javac EmployManagementSystem.java'
	}
	stage('Run'){
		sh 'java EmployManagementSystem'
	}
					
	stage('Sonarqube') {
   	 environment {
     	   scannerHome = tool 'SonarQubeScanner'
  	  }
  	  steps {
  	      withSonarQubeEnv('sonarqube') {
  	          sh "${scannerHome}/bin/sonar-scanner"
  	      }
  	      timeout(time: 2, unit: 'MINUTES') {
 	           waitForQualityGate abortPipeline: true
 	       }
	    }
	}
}
	}
}
