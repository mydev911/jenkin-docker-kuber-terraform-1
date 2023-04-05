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
        stage('Unit Test maven') {
            steps {
                script{
                    mvnTest()

                }
            }
        }
        stage('Integration Test Maven') {
            steps {
                script{
                    mvnintegrationTest()

                }
            }
        }
    }
}
