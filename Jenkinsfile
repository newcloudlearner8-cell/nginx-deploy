pipeline {
  agent any

  stages {
    stage('Check Cluster') {
      steps {
        sh 'kubectl get nodes'
      }
    }

    stage('Deploy Nginx') {
      steps {
        sh 'kubectl apply -f nginx-deploy.yaml'
      }
    }

    stage('Verify') {
      steps {
        sh '''
          kubectl get pods
          kubectl get svc nginx-jenkins
        '''
      }
    }
  }
}
