pipeline {

	
    agent any
    
    environment{
	    SECRET_TEST = "Secret"
    }
     
    stages {	
			
		stage('Publish') {
			parallel {
				stage('Build for TEST') {
					when {
						branch 'development'
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
						branch 'main'
					}
					steps {
						bat 'echo this is Production Branch'
					}					
				}

			}
		}
	}
}
