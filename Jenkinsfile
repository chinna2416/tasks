pipeline{
    agentany
    stages{
        stage("Checkout"){
            scm checkout
            git 'https://github.com/chinna2416/tasks.git'
        }
        stage("Build"){
            sh "mvn clean package"
        }
    }
    post{
        always{
            echo "hi"
        }
        success{
                mail(to:"sampath760@gmail.com",subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed.")
            }
            failure{
                mail(to:"sampath760@gmail.com",subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed.")
            
            }
        }
    }
