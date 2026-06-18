pipeline{
	agent any
	tools{
	maven 'Maven'}
	stages{
		stage('Checkout'){
		steps{ git branch: 'master' ,url :''}
		}
		stage('Build'){
		steps{ sh 'mvn clean package'}
		}
		stage('Test'){
		steps{ sh 'mvn test' }
		}
		stage('Generate Test Reports'){
		steps{ junit 'target/surefire-reports/*.xml'}
		}
		}
	post{
		success{ echo 'Build and deployement Successfull'}
		failure{ echo 'Build failed'}
		always{
			archiveArtifacts artifacts: 'target/**/*.html',allowEmptyArchive:true}
			}
			}
