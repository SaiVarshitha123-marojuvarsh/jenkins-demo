pipeline{
	agent any
	stages {
		stage('Checkout'){
			steps{
				git branch:'main',url:'https://github.com/SaiVarshitha123-marojuvarsh/jenkins-demo.git'
			}
		}
		stage('Build'){
			steps{
				echo 'Compiling java'
				bat 'javac JenkinsJava.java'
			}
		}
		stage('Run'){
			steps{
				echo 'Running..'
				bat 'java JenkinsJava.java'
			}
		}
	}
	post{
		success{
			echo 'Success'
		}
		failure{
			echo 'Failed'
		}
	}
}