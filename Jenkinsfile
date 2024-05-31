pipeline {
    agent any
    tools {
        maven 'M2_HOME'
    }

	
    
    stages {
        stage('SCM Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main' , url: 'https://github.com/Devolu-shiva/banking-project.git'
		        checkout scm
            }
		}
        stage('Maven Build') {
            steps {
                // Run Maven on a Unix agent.
                sh "mvn package"
            }
		}
	      stage('publish html') {
            steps {
                
               publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/target/banking/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
		}

	    
      stage("Docker build") {
            steps {
     //           sh 'docker version'
               sh "docker build -t devshivadevops96/bankhub:1.0 ."
       //       sh 'docker image list'
        //        sh "docker tag dprasaddevops/bankapp-eta-app:${BUILD_NUMBER} dprasaddevops/bankapp-eta-app:latest"
           }
        }
      stage('Login2DockerHub and Push the Image') {
//    steps {
  //      script {
    //        // Retrieve Docker Hub credentials from Jenkins credentials
      //      withCredentials([usernamePassword(credentialsId: 'docker-login-credentials', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
//                echo "Docker Hub Username: $DOCKER_USERNAME"
  //              echo "Docker Hub Password: $DOCKER_PASSWORD"
    //            
      //          sh "docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD"
	//	sh "docker push dprasaddevops/bankapp-eta-app:latest"
 //           }
   //     }
    //}
//}
		
//		stage('Deploy to Kubernetes') {
  //          steps {
    //            script {
      //              kubeconfig(credentialsId: 'k8s', serverUrl: '') {
        //                sh 'kubectl apply -f kubernetesdeploy.yaml'
          //          } 
            //    }
 //           }
 //       }
    }
}
