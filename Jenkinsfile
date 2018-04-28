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
            }
        }
        stage('Deploy') {
            steps {
             echo 'deploying..'
step([$class: "RundeckNotifier",  
             jobId: "1",
             nodeFilters: "",
      		rundeckInstance: "Default",
      		shouldFailTheBuild: true,
      		shouldWaitForRundeckJob: true,
      		tags: "",
      		tailLog: true])
    		}
    	}
	}
}
