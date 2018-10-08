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
				echo 'Sending email...'
			
			catch(err) {
				echo 'error'
				throw err
			}
			finally{
				step([$class: 'Mailer', notifyEveryUnstableBuild: false, recipients: 'rodrigo.sipriano@yaman.com.br', sendToIndividuals: true])
			}
		}
		
	}
}