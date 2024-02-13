pipeline{
  agent any
  environment{
    SCANNER_HOME= tool 'sonar-scanner'
  }
  stages{
    stage("Clean Workspace){
          steps{
            cleanWs()
          }
    }
    stage("Checkout from Git"){
      steps{
        git branch: 'main', url:'https://github.com/Yatingambhir85/practice-jenkins-cicd'
      }
    }
    stage("SonarQube Analysis"){
      steps{
        withSonarQubeEnv('SonarQube-Server'){
          sh '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=carvilla-cicd \ -Dsonar.projectKey=carvilla-cicd'''
        }
      }
    }
}
