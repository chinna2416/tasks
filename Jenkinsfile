pipeline{
    agentany
    stages{
        stage("scm checkout"){
            git 'https://github.com/chinna2416/tasks.git'
        }
        stage("Build"){
            sh "mvn compile package"
        }
    }
    post{
        always{
            echo "hi"
        }
        notifications{
            success{
                mail(to:"sampath760@gmail.com",subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed.")
            }
            
            }
        }
    }
        
