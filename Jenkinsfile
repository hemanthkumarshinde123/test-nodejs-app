pipeline{

agent any

tools{
maven 'maven3.8.7'

}

triggers{
pollSCM('* * * * *')
}

options{
timestamps()
buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5'))
}

stages{

  stage('CheckOutCode'){
    steps{
    git credentialsId: 'git_credentials', url: 'https://github.com/sivakumar9550/maven-web-application.git'
  }
  }
  
  stage('Build'){
  steps{
  sh  "mvn clean package"
  }
  }
}
