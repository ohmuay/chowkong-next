pipeline {
    agent any

    // tools {nodejs "Your Node JS Installation Name"}
    tools {nodejs "nodejs"}

    stages {

        stage('Preparation'){
            steps {
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
                sh 'npm run start'
                // sh 'pm2 start npm --name "nextjs" --interpreter node -- start'
                // sh 'pm2 show nextjs'
            }
        }
    }
}
