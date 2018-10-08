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
		stage('Send email') {
			def mailRecipients = "rodrigo.sipriano@yaman.com.br"
			def jobName = currentBuild.fullDisplayName
			
			emailext body: '''${SCRIPT, template ="groovy-html.template"}''',
				mimeType: 'text/html',
				subject: "[Jenkins] ${jobName}",
				to: "${mailRecipients}",
				replyTo: "${mailRecipients}",
				recipientProviders: [[$class: 'CulpritsRecipientProvider']]
		}
	}
}
