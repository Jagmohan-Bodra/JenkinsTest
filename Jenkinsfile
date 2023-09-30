// Publish profiles 


pipeline {

  agent {label "WIN-CICD"}
  
  
	stages {	
				
		stage('Publish') {
			parallel {
				stage('Build for TEST') {
					when {
						branch 'test'
					}
					steps {
						bat 'echo test branch'
					}					
				}
				stage('Build for STAGE') {
					when {
						branch 'stage'
					}
					steps {
						bat 'echo stage branch direct change'
					}					
				}
				stage('Build for PRODUCTION') {
					when {
						branch 'master'
					}
					steps {
						bat 'echo master'
					}					
				}
			}
		}
	}
	post { 
        always { 
            cleanWs()
        }
    }
}
