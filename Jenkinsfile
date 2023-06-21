pipeline{
  agent any
  
  stages {
    stage ("Build"){
      steps {
        sh 'echo "FFF"'   
      }
    }
    
    stage ('Docker'){
      steps{
        withCredentials([usernamePassword(credentialsId: 'personal-docker-creds', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
          sh "echo ${DOCKER_USERNAME}"
        }
      }
    }
    
  }
}
