node {
	stage('Clone'){
	git 'https://github.com/steevCpp/my-jenkins-file'
	}
	stage('Build'){
		sh label:'', script:'javac Main.java'
	}
	stage('Run'){
	sh label:'', script: 'java Main'
	}

}
