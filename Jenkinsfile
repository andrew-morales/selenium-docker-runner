pipeline{
	agent any
	stages{
		stage("Run Test"){
			steps{
				sh "docker-compose up"
				chmod "777 SELENIUM_DOCKER_RUNNER"
				chmod "777 SELENIUM_DOCKER_RUNNER@tmp"
			}
		}
		stage("Bring Grid Down"){
			steps{
				sh "docker-compose down"
			}
		}
	}
}