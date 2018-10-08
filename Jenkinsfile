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
			steps {
				echo 'Sending email...'
				jobStarted()
			}
		}
	}
	def jobStarted(){
					emailext (
						subject: "STARTED: Job test build 1'",
						body: """<p>STARTED: Job test:</p>
						<p>Check console output at it doesn't matter for now</a>"</p>""",
						recipientProviders: "=|"
					)
				}
}