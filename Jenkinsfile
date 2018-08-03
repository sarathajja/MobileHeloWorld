properties([pipelineTriggers([githubPush()])])

pipeline{
    agent any
    stages{
        stage('Build'){
            
            steps{
                echo "Master branch name"
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
