pipeline {

	agent any
	
	stages {

		stage ('Build stage') {

			steps {

				sh "mvn -B -DskipTests clean package"
				slackSend channel: 'jen-slackintegration', message: 'Build started'
                   }
			post {
				success {
					archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false, fingerprint: true,onlyIfSuccessful: true
				}
					
			}


		                      }
		stage('Testing') {
		
			steps {


				sh "mvn test"

				  }

			


                           }                    





	}
}
