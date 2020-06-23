node {
   environment {
    registryCredential = 'nexus-credentials'
    CI = 'true'
    echo "Branch: ${env.BRANCH_NAME}"
  }

  stage('Git Checkout') {
    try {
        //git credentialsId: 'git-token', url: ''
        checkout scm
      } catch(err) {
         sh "echo error ao fazer checkout!"
      }
    }

  stage('Deploy Checkmarx') {
    try {
       
      } catch(err) {
         sh "echo error ao fazer Deploy Checkmarx!"
      }
    }

  stage('Docker Push Nexus API') {
    try {
       script {
        withDockerServer([uri: "tcp://0.0.0.0:2375"]) {
          withDockerRegistry([credentialsId: 'nexus-credentials', url: ""]) {
           
          }
        }
      }
    } catch(err) {
        sh "echo error ao realizar pushing para nexus!"
      }
    }

}