pipeline{
	agent any
	stages{
		stage("Pull latest image"){
			steps{
				bat "docker pull asuhail8/sel-doc"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up"
			}
		}
		stage("Stop Test"){
			steps{
				bat "docker-compose down"
			}
		}
			}
}