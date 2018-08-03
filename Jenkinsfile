properties([pipelineTriggers([githubPush()])])

pipeline{
    agent any
    stages{
        stage('Build'){

            steps{
	    	echo "Branch related pipeline"
                checkout scm
                bat 'gradlew.bat build'
            }
        }

        stage("Run UI Tests"){
            steps{
                bat 'gradlew.bat connectedAndroidTest'
            }
        }

        stage("Clean up"){
            steps{
                cleanWs()
            }
        }
    }
}
