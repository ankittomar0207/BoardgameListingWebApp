pipeline {
    agent any
    
    tools { 
        maven 'Maven 3.9.0' 
        jdk 'jdk11' 
    }
    

    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/Krishpluto/BoardgameListingWebApp.git'
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
                sh "mvn install"
            }
        }
    }
    
}
