pipeline{
	agent any
	stages{
		stage("Pull latest image"){
			steps{
				sh "docker pull asuhail8/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d selenium-hub chrome firefox edge"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up search-module"
			}
		}
			}

	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			emailext attachLog: true, attachmentsPattern: 'output/search-module/emailable-report.html', body: '', subject: '', to: 'Abdulla.suhail8@gmail.com'
			sh "docker-compose down"
		}
	}
}
