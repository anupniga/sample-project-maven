pipeline {
 agent any
 stages {
  stage('SCM checkout') {
   steps {
    git branch: 'master', url: 'https://github.com/anupniga/sample-project-maven'
   }
  }
  stage('sonar and maven package') {
   steps{
   withSonarQubeEnv('sonar') {
      withMaven(maven:'localmaven') {
	    sh 'mvn install sonar:sonar'
	  }
   }
   }
  }
}
}
