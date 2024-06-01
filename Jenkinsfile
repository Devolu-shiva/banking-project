pipeline {
    agent any
    tools {
        maven 'M2_HOME'
    }

	
    
    stages {
        stage('SCM Checkout') {
            steps {
        
                git branch: 'main' , url: 'https://github.com/Devolu-shiva/banking-project.git'
		
            }
		}
        stage('Maven Build') {
            steps {
                
                sh "mvn package"
            }
		}
	 

    }
}
