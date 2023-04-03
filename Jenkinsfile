@Library('Jenkins-shared-library') _

pipeline {
    agent any
    
    stages {
        stage('Git Checkout') {
            steps {
                gitCheckout([
                    url: 'https://github.com/mydev911/jenkin-docker-kuber-terraform-1.git',
                    branch: 'main'
                ])
            }
        }
    }
}
