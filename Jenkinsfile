properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('Test') {    
    git credentialsId: 'git2', url: 'https://github.com/Prerana2205/java-project'
    sh 'ant -buildfile test.xml'
 }
}
