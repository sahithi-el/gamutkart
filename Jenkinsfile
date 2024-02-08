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
                sh 'cp /home/staragile/builds/workspace/sample-declarative1/target/gamutkart.war /opt/tomcat/webapps
            }

        } 
  }
}
