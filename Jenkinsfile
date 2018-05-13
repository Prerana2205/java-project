properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('Unit Tests') {    
	    git credentialsId: 'git2', url: 'https://github.com/Prerana2205/java-project'
    	    sh 'ant -f test.xml -v'
    	    junit 'reports/*.xml'
	}
	stage('Build') {
	    sh 'ant -f build.xml -v'
	}
	stage('Deploy') {
	    sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar s3://prerana-jenkins/jenkins/'
	}
}
