pipeline {
    agent any
    environment {
        name ='gaurav'
    }
    parameters {
        string(name:'person', defaultValue:'Saurav Sharma', description:"who are you?")
        booleanParam(name:'ismale', defaultValue:'true', description:"")
    }
    stages {
        stage('RUN A COMMAND') {
            steps {
                sh'''
                date
                pwd
                ls
                '''
            }
        }
         stage('Environment Variables') {
             environment {
                 username ='myusername'
             }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
         stage('BUILD') {
            steps {
                echo 'build'
            }
        }
         stage('DEPLOY ON TEST') {
            steps {
                echo 'deploy on test'
            }
        }
         stage('DEPLOY ON PROD') {
            steps {
                echo 'deploy on prod'
            }
        }
         stage('continue?') {
            input {
                message "should we continue?"
                ok "Yes we should"
            }
            steps {
                echo 'deploy on prod'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Success'
        }
    }
}
