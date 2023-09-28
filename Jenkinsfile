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
						bat 'echo this is Development Branch'
					}					
				}
				stage('Build for STAGE') {
					when {
						branch 'stage'
					}
					steps {
						bat 'echo this is Staging Branch'
					}					
				}
				stage('Build for PRODUCTION') {
					when {
						branch 'master'
					}
					steps {
						bat 'echo this is Production Branch'
					}					
				}

			}
		}
	}
}
