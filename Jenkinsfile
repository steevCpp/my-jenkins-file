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
        sh label :'', script :'sonar.projectKey = Projet-jenkins-sonar \
sonar.login = admin \
sonar.password = sonar \
sonar.sources = /var/lib/jenkins/workspace/testing \
sonar.host.url = http://79.137.37.34:9000 '
        }

}
