pipeline {
  agent {
     node {
        label 'workstation'
     }
  }

  stages {

    stage('Build Docker Image') {
      steps {
        sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 693381842268.dkr.ecr.us-east-1.amazonaws.com'
        sh 'docker build -t 693381842268.dkr.ecr.us-east-1.amazonaws.com/schema-loader:latest .'
        sh 'docker push 693381842268.dkr.ecr.us-east-1.amazonaws.com/schema-loader:latest'
      }
    }

  }

}
