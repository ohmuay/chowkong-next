pipeline {
    agent any

    // tools {nodejs "Your Node JS Installation Name"}
    tools {nodejs "nodejs"}

    stages {
        stage('Build') { 
            steps {
                sh 'npm run build'
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
