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
						bat 'testbranch'
					}					
				}
				stage('Build for STAGE') {
					when {
						branch 'stage'
					}
					steps {
						bat 'stage branch'
					}					
				}
				stage('Build for PRODUCTION') {
					when {
						branch 'master'
					}
					steps {
						bat 'master branch'
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
