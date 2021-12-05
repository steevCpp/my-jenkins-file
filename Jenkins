node {
	stage('Clone'){
	git 'https://git@github.com:steevCpp/my-jenkins-file.git'
	}
	stage('Build'){
		sh label:'', script:'javac Main.java'
	}
	stage('Run'){
	sh label:'', script: 'java Main'
	}

}
