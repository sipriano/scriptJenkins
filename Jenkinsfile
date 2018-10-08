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
				steps {echo 'Sending email...'
				node {
    				try {
        				sh 'exit 1'
        				currentBuild.result = 'SUCCESS'
    				} catch (any) {
        				currentBuild.result = 'FAILURE'
        				throw any //rethrow exception to prevent the build from proceeding
    				} finally {
        				step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'rodrigo.sipriano@yaman.com.br', sendToIndividuals: true])
    				}
				}
			}
		}
		}
}