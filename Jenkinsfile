pipeline{
    agent any

    stages {

        stage('Git Checkout'){
            
            steps{

                script {
                    gitcheckout
                       branch: "main"
                       url: "https://github.com/mydev911/jenkin-docker-kuber-terraform-1.git"
                }
            }

        }
    }
}