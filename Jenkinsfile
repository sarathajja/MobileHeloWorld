properties([pipelineTriggers([githubPush()])])

pipeline{
    agent any
    stages{
        stage('Build'){

            steps{
		     
	    	echo "Branch related pipeline"
		echo 'Pulling...' + env.BRANCH_NAME
		'printenv'
                checkout scm
              
        }

       stage("Clean up"){
            steps{
                cleanWs()
            }
        }
    }
}
