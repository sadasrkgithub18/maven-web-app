@Library('SRKIT-Lib') _

pipeline {
    agent any    
    tools{
        maven "Maven-3.9.4"
    }
    stages {
        stage('Clone') {
            steps {
                  git branch: 'main', credentialsId: '50137803-2c55-4259-9634-6054953641c2', url: 'https://github.com/sadasrkgithub18/maven-web-app.git'
            }
        }
        stage('Maven Build'){
            steps{
              mavenBuild()
            }
        }
		stage('Code Review'){
			steps{
				sonarQube()
			}
		}
    }
}
