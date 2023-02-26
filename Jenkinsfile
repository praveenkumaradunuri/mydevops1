pipeline {
    agent any
    environment {
        name = 'pavan'   
    }
    parameters {
        string(name: 'Person', defaultValue: 'pavan', description: 'Who are you')
        booleanParam(name: 'isMale', defaultValue: 'Yes', description: '')
        choice(name: 'city', choices: ['jaipur','Hyderabad','pune','BLR'],description: "")
    }
    stages {
        stage('Run A Command') {
            steps {
                sh '''
                date
                ls
                pwd
                cal 2023
                '''
            }
        }
        stage('Environment variable') {
            environment {
                username = 'naveen'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                sh 'echo "${name}"'
                sh 'echo "${Person}"'
            }
        }
        stage('Deploy on Test') {
            steps {
                echo 'Deploy on Test'
            }
        }
        stage('continue') {
            input {
                message "should we continue?"
                ok "yes we should"
            }
            steps {
                echo 'Deploy on Test'
            }
        }
        stage('Deploy on Prod') {
            steps {
                echo 'Deploy on Prod'
            }
        }
    }
    post{
        always{
            echo 'i Will always say hello again'
        }
        failure {
            echo 'failure'
        }
        success {
            echo 'Seccess'
        }
    }
}
