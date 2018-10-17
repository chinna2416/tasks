pipeline {
  agent any
  stages {
      stage("scm checkout"){
          steps{
              git 'https://github.com/chinna2416/tasks.git'
          }
      }
    stage("Build") {
      steps {
        sh 'mvn clean package'
      }
    }
    
  }
  post {
    always {
        echo "hey"
    }
    success {
      mail to:"sampath4ms@gmail.com", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
    }
    failure {
      mail to:"sampath4ms@gmail.com", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
       }
  }
}
