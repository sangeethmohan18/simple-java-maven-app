pipeline {

	agent { label 'slave1'}
	
	stages {

		stage ('Build stage') {

			steps {

				sh "mvn -B -DskipTests clean package"
                   }


		                      }
		stage('Testing') {
		
			steps {


				sh "mvn test"

				  }

			post {
			
				always{

					junit 'target/surefire-reports/*.xml'


   						}	  
               	}



                           }                    





	}
}
