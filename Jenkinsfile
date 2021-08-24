pipeline {
  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/khouloudRb/GMC_k8s.git'
      }
    }

    stage('Deploy Secret') {
      steps {
        script {
          kubernetesDeploy(configs: "mongo-secret.yaml,", kubeconfigId: "eab67c1c-e532-434a-abbb-53b65f8f9cd3")
        }
      }
    }
    stage('Deploy Backend') {
      steps {
        script {
          kubernetesDeploy(configs: "backend.yaml", kubeconfigId: "eab67c1c-e532-434a-abbb-53b65f8f9cd3")
        }
      }
    }
    stage('Deploy Frontend') {
      steps {
        script {
          kubernetesDeploy(configs: "frontend.yaml", kubeconfigId: "eab67c1c-e532-434a-abbb-53b65f8f9cd3")
        }
      }
    }

  }

}
