properties([pipelineTriggers([githubPush()])])
pipeline {
  agent any
  stages {
    stage('Source') {
      steps {
        $class: 'GitSCM',
        git 'https://github.com/arjundevop/pipeline.git'
      }
    }
    stage('build') {
      steps {
        sh 'mvn -version'
        sh 'mvn clean install'
    
      }
    }
   }
  }
