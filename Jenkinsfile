pipeline {
    agent any
    
    tools { 
        maven 'maven3.9.0' 
        jdk 'myjava' 
    }
    

    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/Krishpluto/BoardgameListingWebApp.git'
            }
        }

        stage('Clean target dir') {
            steps {
                sh "mvn clean"
            }
		}	
           stage('validate maven ') {
            steps {
                sh "mvn validate"
            } 
        }			
        
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
         stage('Compile') {
            steps {
                sh "mvn compile"
            }
        }
        stage('Package') {
            steps {
                sh "mvn package"
            }
        }
        stage('Install') {
            steps {
                sh "mvn install -DskipTests=true"
            }
        }
    }
    
}
