pipeline{
	agent any
	stages{
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
