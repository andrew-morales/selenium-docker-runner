pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d --scale chrome=4 --scale firefox=4 hub chrome firefox"
			}
		}
		stage("Run The Test"){
			steps{
				sh "docker-compose up search-module book-flight-module"
			}
		}
		stage("Stop The Grid"){
			steps{
				sh "docker-compose down"
			}
		}
	}
}