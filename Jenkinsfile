pipeline {
  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/khouloudRb/GMC_k8s.git'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "frontend.yaml,backend.yaml,mongo-secret.yaml,", kubeconfigId: "eab67c1c-e532-434a-abbb-53b65f8f9cd3")
        }
      }
    }

  }

}
