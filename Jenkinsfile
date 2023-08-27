pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Goodbye') {
            steps {
                echo 'good bye'
            }
        }
        stage('sh') {
            steps {
                
                sh 'echo \'from shell\''
            }
        }
        
    }
        
}
