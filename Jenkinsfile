pipeline {
    agent any

    // tools {nodejs "Your Node JS Installation Name"}
    tools {nodejs "nodejs"}

    stages {

        stage('Preparation'){
            steps {
                sh 'npm install --global pm2'
                sh 'pm2 stop all'
                sh 'npm install'
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
                sh 'pm2 start yarn --name "nextjs" --interpreter bash -- start'
                sh 'pm2 show nextjs'
            }
        }
    }
}
