pipeline {

    agent{ 
      label 'jenkins-agent' }
environment {
        SCANNER_HOME=tool 'sonar-scanner'
    }
  

    stages{

         stage('Fetch Code') {
             steps {
                 git branch: 'main', url: 'https://github.com/Oussama-gharbi/game2048.git'
             }
	 }

   stage('Sonarqube'){
    steps{
    withSonarQubeEnv('sonar-server') {
sh '''$SCANNER_HOME/bin/sonar-scanner \
  -Dsonar.projectKey=game2048 \
  -Dsonar.sources=src/ \
  -Dsonar.host.url=http://10.165.147.223:9000 \
  -Dsonar.login=b431173bceb26d1d81d26354bf51fdf26f1d063a'''
}
}
}
    

}
}


