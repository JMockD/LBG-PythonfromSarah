pipeline {
    
    agent any
    
    stages {
        stage('build and run containers') {
            steps {
                sh '''
                docker build -t gcr.io/lbg-mea-11/sm-img:v1 .
                docker push  gcr.io/lbg-mea-11/sm-img:v1
                '''
	    }
	}  
        stage('clean') {
			steps {
				sh 'docker rmi gcr.io/lbg-mea-11/sm-img:v1'
			}
		}
	}
}    
