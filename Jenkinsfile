pipeline{
	agent any
	stages{
		stage("Pull latest image"){
			steps{
				bat "docker pull asuhail8/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module"
			}
		}
			}

	post{
		always{
			archiveArtifacts artifacts: 'C:/Users/abdul/eclipse-workspace/selenium-doc/output/**'
			bat "docker-compose down"
		}
	}
}