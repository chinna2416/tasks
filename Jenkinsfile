pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                        git 'https://github.com/chinna2416/tasks.git'
            }
            stage('Compile-Package'){
               steps {
                           sh 'mvn package'
               }
            }
        }
    }
    post {
        always {
            junit '**/target/*.xml'
        }
        failure {
            mail to: sampath760@gmail.com, subject: 'The Pipeline failed '
        }
        }
