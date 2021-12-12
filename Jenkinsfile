

node
{
    stage('clonning from GIT'){
git branch: 'master', credentialsId: 'GIT_REPO', url: 'https://github.com/steevCpp/my-jenkins-file'
     }

stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarQube'
      withSonarQubeEnv('SonarQube') {
      sh """/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/Ssonarqube/bin/sonar-scanner \
     -D sonar.projectVersion=1.0-SNAPSHOT \
       -D sonar.login=admin \
      -D sonar.password=sonar \
      -D sonar.projectBaseDir=/var/lib/jenkins/workspace/jenkins-sonar/ \
        -D sonar.projectKey=sonar-jenkikns \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.sources=. \
        -D sonar.host.url=http://79.137.37.34:9000/"""
        }
}
}
