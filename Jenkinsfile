properties([pipelineTriggers([githubPush()])])

pipeline{
    agent any
    stages{
        
        stage("check out"){
            steps{
               checkout scm
            }
        }
        
        stage('Build'){
            
            steps{
                bat 'gradlew.bat installDebug'
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
