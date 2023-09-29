pipeline {
    agent any

    tools {
        nodejs '20.4.0'
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Ivy23-git/gallery'
            }
        }

         stage('Install Dependencies') {
            steps {
               
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
             
                sh 'npm test'
            }
        }
  }
    post {
        always {
            slackSend( channel: 'ivy_ip1', 
            color: 'good, warning, danger.', 
            message: 'output', teamDomain: 'ivyip1', 
            tokenCredentialId: '971965d1-51fe-484b-84a6-768f584b7216'
            )
        }
    }
}
