pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
            }
        }
		stage('Stage 2') {
			steps {
                           echo 'stage 2'
			}
		}
                stage('Stage 3') {
                        steps {
                         echo'build on commit'   
                        }
                }
           stage('Stage 4') {
                 jobStarted()
 }
      
             def jobStarted(){
                  emailext (
                  subject: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                  body: """<p>STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
                  <p>Check console output at "<a href="${env.BUILD_URL}">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>"</p>""",
                  recipientProviders: [[$class: 'DevelopersRecipientProvider']]
                  )
             }
}
}
