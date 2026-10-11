pipeline{
    agent any
     
    stages{
        stage("Install NPM Dependencies"){
            steps{
                
                bat "npm install"

            }
        } 
        stage("Run Tests"){
            steps{
                
                bat "npm test"

            }
        }
    }
    
}