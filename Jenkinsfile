@Library('Jenkins-shared-library') _

pipeline {
    agent any

    parameters{
        choice(name: 'action', choices : 'create\ndelete', description: 'Choose create/Destroy') 
    }
    
    stages {

        
        stage('Git Checkout') {
            when{ expression { param.action == 'create'}}
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
        stage('Stastic code analysis ') {
            when{ expression { param.action == 'create'}}
            steps {
                script{
                    staticCodeAnalysis()

                }
            }
        }

      
    }
}
