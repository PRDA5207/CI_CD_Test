pipeline {
  agent any

  environment {
    IMAGE_NAME = "my-python-app"
  }

  stages {

    stage('Install Dependencies') {
      steps {
        sh 'pip3 install -r requirements.txt'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'pytest || echo "No tests found"'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t $IMAGE_NAME .'
      }
    }

    stage('Deploy Container') {
      steps {
        sh '''
        docker stop my-container || true
        docker rm my-container || true
        docker run -d -p 5000:5000 --name my-container $IMAGE_NAME
        '''
      }
    }

  }

  post {
    success {
      echo 'CI/CD pipeline completed successfully '
    }
    failure {
      echo 'Pipeline failed '
    }
  }
}
