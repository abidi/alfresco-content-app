pipeline {
    agent {
        docker {
            image 'node:9-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm install -g @angular/cli'
                sh 'ng build --prod'
            }
        }
        stage('Test') {
            steps {
                sh 'ng test'
                sh 'ng e2e'
            }
        }
    }
}
