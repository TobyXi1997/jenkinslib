@Library('jenkinslib')

def tools = new org.devops.tools()
pipeline {
    agent any
    tools {
        maven 'm2' 
    }
    stages {
        stage('Example') {
            steps {
                script{
					tools.PrintMes("this is my lib!")
				}
            }
        }
    }
}
