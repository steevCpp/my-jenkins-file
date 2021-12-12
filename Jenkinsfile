
node
{
    stage('Clone Github'){
git branch: 'master', credentialsId: 'GIT_REPO', url: 'https://github.com/steevCpp/my-jenkins-file'
     }

    stage('Build'){
    sh " javac EmployManagementSystem.java "
     }
     stage('Run'){
    sh " java EmployManagementSystem"
     }
    
stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarqube'
      withSonarQubeEnv('sonarqube') {
      sh """/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonarqube/bin/sonar-scanner \
     -D sonar.projectVersion=1.0-SNAPSHOT \
       -D sonar.login=admin \
      -D sonar.password=sonar \
      -D sonar.projectBaseDir=/var/lib/jenkins/workspace/Projet-Jenkins-Sonar \
        -D sonar.projectKey=sonar-jenkikns \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.java.binaries=.  \
        -D sonar.sources=. \
        -D sonar.host.url=http://79.137.37.34:9000/"""
        }
}
}
