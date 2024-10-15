pipeline{
    agent any 
    stages{
        stage("NPM Install"){
            steps{
                bat 'npm install'
            }
        }
        stage('Parralel Execution'){ 
            parallel {
                stage("Run npm audit tests"){
                    steps{
                        bat 'npm audit'
                    }
                }
                stage("Execute tests"){
                    steps{
                        bat 'npm test'
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            step {
                echo 'Deploy to Staging'
            }
        }
        stage('Deploy to Production') {
            step {
                echo 'Deploy to Production'
            }
        }
    }
}