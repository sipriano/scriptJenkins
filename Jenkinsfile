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
				steps{
					post {
        				success {
            				mail to:"rodrigo.sipriano@yaman.com.br", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
        				}
        				failure {
            				mail to:"rodrigo.sipriano@yaman.com.br", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
        				}
					}
				}
		}
}
}