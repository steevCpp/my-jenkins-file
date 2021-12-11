node {
	stage('Clone'){
	git 'https://github.com/steevCpp/my-jenkins-file'
	}
	stage('Build'){
		sh label:'', script:'javac EmployManagementSystem.java'
	}
	stage('Run'){
	sh label:'', script: 'java EmployManagementSystem'
	}

        stage('Qualite'){
  	environment {
   	 SCANNER_HOME = tool 'SonarQubeScanner'
         }
	
	withSonarQuebEnv(sonarqube)(
	 
	 sh label:'', script :' ${SCANNER_HOME}/bin/sonar-scanner \
	-Dsonar.projectKey=Projet-jenkins-sonar \
	-Dsonar.login=admin \
	-Dsonar.password=sonar \
	-Dsonar.sources=/var/lib/jenkins/workspace/my-jenkins-file \
	-Dsonar.host.url=http://79.137.37.34:9000 '
	 )
        }

}

