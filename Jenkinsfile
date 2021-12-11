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
        sh label :'', script :'sonar-scanner \
  -Dsonar.projectKey=Projet-jenkins-sonar \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://79.137.37.34:9000 \
  -Dsonar.login=6dbf3d53790a5b319f325f33f0d43c7f1de14ed3 '
        }

}
