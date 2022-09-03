pipeline {
    agent any

    // tools {nodejs "Your Node JS Installation Name"}
    tools {nodejs "nodejs"}

    stages {

        environment{
            NODE_ENV=production
        }

        stage('Preparation'){
            steps {
                sh 'npm install --production'
                sh 'npm run lint'
            }
        }

        stage('Build') { 
            steps {
                sh 'NODE_ENV=production npm run build'
            }
        }
        // stage('Test') { 
        //     steps {
        //         // 
        //     }
        // }
        stage('Deploy') { 
            steps {
                sh 'npm run start'
            }
        }
    }
}
