pipeline {

    agent any

    stages{

        stage("buildApp"){
            steps{
                script {
                    sh "./mvnw package"
                    
                }
            }
        }
        stage("codeAnalysis"){
          environment {
              def sonarHome = tool name: 'SonarScanner'

            }
            
            steps{
                script {
                    sh "${sonarHome}/bin/sonar-scanner "
                }
            }
        }
    }
}