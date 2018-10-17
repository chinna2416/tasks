pipeline{
    agent any
    stages{
        stage('scm checkout'){
            steps{
               git 'https://github.com/chinna2416/tasks.git'
            }
        }
          stage('Build'){
            steps{
                sh 'mvn clean install'
            }
        }
        post{
            always{
                echi "hi"
            }
            stage{
            success{
                mail(to:"sampath760@gmail.com",subject:"SUCCESS: ${currentBuild.fullDisplayName}",
                body: " we passed.")
            }
        }
     }
  }
}
