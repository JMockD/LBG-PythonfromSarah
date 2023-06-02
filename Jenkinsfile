pipeline {
    
    agent any
    
    stages {
        stage('pre-build cleanup') {
            steps {
                sh 'docker system prune -f'
            }
        }    
        
        stage('build and run containers') {
            steps {
                sh '''
                docker build -t gcr.io/lbg-mea-11/sm-img:v1 .
                docker run -d -p 5000:8080 --name lbg-app lbg-app:v1
                docker push  gcr.io/lbg-mea-11/sm-img:v1
                '''
            }
        }
    }
}   
