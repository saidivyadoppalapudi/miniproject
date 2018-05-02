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
					script {
   			 step([$class: "RundeckNotifier",
          			includeRundeckLogs: true,
          			jobId: "1",
          			nodeFilters: "",
          			options: """
                   	PARAM_1=value1
                   	PARAM_2=value2
                   	PARAM_3=
                   	""",
          			rundeckInstance: "Default",
          			shouldFailTheBuild: true,
          			shouldWaitForRundeckJob: true,
          			tags: "",
          			tailLog: true])
  					}             
    		}
		}
	}
}
