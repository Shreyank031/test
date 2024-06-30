pipeline {
    agent any 
    triggers {
        pollSCM '* * * * *'
    }
     stages {
        stage('Build'){
            steps {
                echo Building...
                sh '''
                echo 'Building some stuff..'
                '''
            }
        }
        stage('Approval') {
           steps {
              timeout(time: 15, unit: MINUTES) {
              input message: 'Do you want to approve the deployment?', ok: 'Yes'
              }
           } 
        }
        stage('Testing') {
            steps {
                echo Testing...
                sh '''
                echo Testing some things out
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo Deploying...
                sh '''
                echo Doing Deployment stuff....    
                '''
            }
        }
    }
}
