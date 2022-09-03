pipeline {
    agent any

    // tools {nodejs "Your Node JS Installation Name"}
    tools {nodejs "nodejs"}

    stages {

        stage('Preparation'){
            steps {
                sh 'npm install --global pm2'
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
                sh 'pm2 start npm --name "nextjs" --interpreter run -- start'
                sh 'pm2 show nextjs'
            }
        }
    }
}
