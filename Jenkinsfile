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
				env.ForEmailPlugin = env.WORKSPACE
				body: "teste",
				subject: currentBuild.currentResult + " : " + env.JOB_NAME,
				to: 'rodrigo.sipriano@yaman.com.br'
		}
	}
}