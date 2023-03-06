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
    git credentialsId: 'S_Hemanth_kumar_git_credentials', url: 'https://github.com/hemanthkumarshinde123/test-nodejs-app.git'
  }
  }
  
  stage('Build'){
  steps{
  sh  "mvn clean package"
  }
  }
}
