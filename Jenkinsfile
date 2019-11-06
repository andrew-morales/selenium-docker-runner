pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run The Test"){
			steps{
				sh "docker-compose up --scale chrome=4 --scale firefox=4 search-module1 search-module2"
			}
		}
		stage("Stop The Grid"){
			steps{
				sh "docker-compose down"
			}
		}
	}
}