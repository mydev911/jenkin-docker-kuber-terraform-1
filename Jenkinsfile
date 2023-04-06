@Library('Jenkins-shared-library') _

pipeline {
    agent any

    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy') 
    }
    
    stages {

        when{ expression { param.action == 'create'}}
        stage('Git Checkout') {
            steps {
                gitCheckout([
                    url: 'https://github.com/mydev911/jenkin-docker-kuber-terraform-1.git',
                    branch: 'main'
                ])
            }
        }
        stage('Unit Test maven') {

            when{ expression { param.action == 'create'}}
            steps {
                script{
                    mvnTest()

                }
            }
        }
        stage('Integration Test Maven') {
            when{ expression { param.action == 'create'}}
            steps {
                script{
                    mvnintegrationTest()

                }
            }
        }
    }
}
