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
	      stage('publish html') {
            steps {
                
               publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/target/banking/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
		}

	    

    }
}
