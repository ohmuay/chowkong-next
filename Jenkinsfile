pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'npm build'
            }
        }
        stage('Test') { 
            steps {
                // 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'npm start'
            }
        }
    }
}
