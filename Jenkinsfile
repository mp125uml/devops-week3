properties([pipelineTriggers([githubPush()])])
 
pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        /* checkout repo */
        stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'main']],
                 userRemoteConfigs: [[
                    url: 'https://github.com/mp125uml/devops-week3.git',
                    credentialsId: '',
                 ]]
                ])
            }
        }
         stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}