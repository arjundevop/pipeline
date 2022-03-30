properties([pipelineTriggers([githubPush()])])
pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
            steps {
                 git '$git_repo'
            }
    }
    
    stage('build') {
      steps {
        sh 'mvn $version'
        sh 'mvn clean $mvn'
    
      }
    }
    stage('dockerbuild')
    {
     steps {
         sh 'docker build -t tomcat .'
     }   
    }
   }
  }
