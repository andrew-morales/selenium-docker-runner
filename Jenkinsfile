pipeline{
	agent any
	stages{
		stage("Pull Latest asmorales/selenium-docker Image"){
			steps{
				sh "docker pull asmorales/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run The Test"){
			steps{
				sh "docker-compose up search-module1 search-module2"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}
}