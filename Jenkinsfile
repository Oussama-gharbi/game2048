pipeline {

    agent{ 
      label 'jenkins-agent' }
  tools{
        nodejs 'nodejs16'
    }
environment {
        SCANNER_HOME=tool 'sonar-scanner'
    }
  

    stages{

         stage('Fetch Code') {
             steps {
                 git branch: 'main', url: 'https://github.com/Oussama-gharbi/game2048.git'
             }
	 }

   stage("Sonarqube Analysis "){
            steps{
                withSonarQubeEnv('sonar-server') {
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=game2048 \
                    -Dsonar.projectKey=game2048 '''
                }
            }
        }
}
}


