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
        
        script {
          def dockerTool = tool name: 'docker-latest-tool', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
          env.PATH = "${dockerTool}/bin:${env.PATH}"
        }
        
        withCredentials([usernamePassword(credentialsId: 'personal-docker-hub-creds', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
          sh "echo ${DOCKER_USERNAME}"
        }
        
        sh "docker --version"
      }
    }
    
  }
}
