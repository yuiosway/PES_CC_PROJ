pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                bat 'copy.bat'
                bat 'docker build -t uc1 ./uc1'
                bat 'docker tag uc1 akarshj21/uc1:latest'
                bat 'docker push akarshj21/uc1:latest'
                bat 'docker build -t uc2 ./uc2'
                bat 'docker tag uc1 akarshj21/uc2:latest'
                bat 'docker push akarshj21/uc2:latest'
                bat 'docker build -t uc3 ./uc3'
                bat 'docker tag uc3 akarshj21/uc3:latest'
                bat 'docker push akarshj21/uc3:latest'
                bat 'docker build -t frontend ./frontend'
                bat 'docker tag frontend abishekd/frontend:latest'
            }
        }
        
        stage('Deploy') {
            steps {
                 bat 'kubectl apply -f kubernetes.yaml'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
