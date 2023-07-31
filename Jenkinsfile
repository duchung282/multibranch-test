pipeline {

  agent any
  
	options {
		buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
	}

	stages {
		stage('Hello') {
			steps {
				script {
				  echo "git Message: ${GIT_BRANCH}"
				}
			}
		}
	
  
		stage('cat README') {
			when {
				branch "fix-*"
			}

			steps {
				sh '''
				  cat README.md
				'''
			}  
		}
	}	
}