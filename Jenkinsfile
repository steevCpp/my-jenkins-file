pipeline {
	agent any

	Stages {
		Stage('Clone'){
			Steps{
		sh "rm -rf"
		sh "git clone https://github.com/steevCpp/my-jenkins-file"
	}
	Stage('build'){
		sh 'javac EmployManagementSystem.java'
	}
	Stage('Run'){
		sh 'java EmployManagementSystem'
	}
					
	Stage('Sonarqube') {
   	 environment {
     	   scannerHome = tool 'SonarQubeScanner'
  	  }
  	  Steps {
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
