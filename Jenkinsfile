def jobName="Bob1-dev_${GIT_BRANCH}"
def unity_version="2021.3.16f1"
def s3PathArmv7 = null
def s3PathArm64 = null

pipeline {

  agent any
  
	options {
		buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
	}

	environment{
	   UNITY_PATH="/Applications/Unity/Hub/Editor/${unity_version}/Unity.app/Contents/MacOS/Unity"
	   workingDir="/Users/falconbuilder/Workspace/hungnd/jenkins/workspace/${jobName}"
	   logDir="/Users/falconbuilder/Workspace/hungnd/jenkins/logs/${jobName}.log"
	}
	
	stages {
		stage('Hello') {
			steps {
				script {
				  echo "Git Branch: ${GIT_BRANCH}"
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