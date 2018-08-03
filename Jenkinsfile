properties([pipelineTriggers([githubPush()])])

pipeline{
    agent any
    stages{
        stage('Build'){

            steps{
		     
	    	echo "Branch related pipeline"
		echo 'Pulling...' + env.BRANCH_NAME
		
                checkout scm
	    }
        }

       stage("Clean up"){
            steps{
		    Script{
			bat 'set > env.txt' 
			for (String i : readFile('env.txt').split("\r?\n")) {
  			println i
}	
		    }
                cleanWs()
            }
        }
    }
}
