pipeline {
    agent any
    environment {
         desig = "Devops"
    }
    parameters {
        string(name: 'person', defaultValue: 'Saurav Sharma', description: 'who are you?')
        booleanParam(name: 'ismale', defaultValue: true, description: '')
        choice(name: 'City', choices: ["Jaipur","Mumbai","Pune"], description: '')
    }
    
    stages {
        stage('Test') {
            steps {
                bat 'wmic computersystem get name'
                bat 'echo %PATH%'
            }
        }
        stage('Env Variabled') {
            environment {
                username = "Trilok"
            }
            steps {
                bat 'echo %BUILD_ID%'
                bat 'echo %desig%'
                bat 'echo %username%'
            }
        }
        stage('Build') {
            steps {
                echo 'Build World'
                bat 'echo %username%'
            }        
        }
        stage('parameters') {
            steps {
                echo 'Deployontest World'
                bat 'echo  %person%'
            }
            
        }
        stage('Continue ?') {
            input {
                message "Shall we continue?"
                ok "Yes we should"
            }
            steps {
                echo 'Deployonprod World'
            }
            
        }
        stage('Deployonprod') {
            steps {
                echo 'Deployonprod World'
            }
            
        }
    }
    post{
        always {
            echo "Hello always"
        }
        failure{
            echo "Hello Failure"
        }
        success{
            echo "Hello Sucess"
        }
    }
}
