pipeline {

	agent any
	
	stages {

		stage ('Build stage') {

			steps {
				echo " ########################################################################"
				echo""
				echo " STARTING THE BUILD"

				sh "mvn -B -DskipTests clean package"
				slackSend channel: 'jen-slackintegration', message: 'Build started'
                   }
			post {
				success {
					echo "#################################################################"
					echo "SUCCESSFULLY ARCHIVED"
					archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false, fingerprint: true,onlyIfSuccessful: true
				}
					
			}


		                      }
		stage('Testing') {
		
			steps {
				
				echo "#######################################################################"
				echo ""
				echo " STARTED TESTING"
				
				sh "mvn test"

				  }
			post {
				success{
					echo "#################################################################"
					echo"TESTING COMPLETED SUCCESSFULLY"
					slackSend channel: 'jen-slackintegration', message: 'Successfully tested'
				}
			}
					

			


                           }                    





	}
}
