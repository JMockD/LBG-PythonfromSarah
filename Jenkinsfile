pipeline {
    
    agent any
    
    stages {
        stage('build and run containers') {
            steps {
                sh '''
                docker build -t gcr.io/lbg-mea-11/sm-img:v1 .
                docker run -d -p 5000:8080 --name sm-lbg-app gcr.io/lbg-mea-11/sm-img:v1
                docker push  gcr.io/lbg-mea-11/sm-img:v1
                '''
            }
        }
    }
}   
