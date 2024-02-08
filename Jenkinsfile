pipeline {
    agent any

//	tools {
//		jdk 'jdk8'
//	}
//	environment {
//		M2_INSTALL = "/usr/bin/mvn"
//	}

    stages {
        stage('Clone-Repo') {
	    	steps {
	        	checkout scm
	    	}
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
		
        stage('Unit Tests') {
            steps {
                sh 'mvn test'
            }
        }

        stage('package') {
            steps {
                sh 'mvn package'
            }
       
       }
        
       stage('Deployment') {
            steps {
                sh 'sshpass -p "staragile" scp target/gamutkart.war staragile@172.31.21.169:/home/staragile/builds/workspace'
            }

        }
  }
}
