pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/harika057/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t harika057/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push harika057/saleor-dashboar:DEV'
            }
        }
    }
}
