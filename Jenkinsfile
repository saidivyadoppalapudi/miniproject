pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            
                echo 'Building....'
                sh 'mvn install'
                echo 'mvn' 

             }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
                logstashSend failBuild: true, maxLines: 1000
            }
        }
        stage('Deploy') {
            steps {
             echo 'deploying..'
    		}
    	}
	}
}
