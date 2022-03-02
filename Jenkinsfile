properties([pipelineTriggers([githubPush()])])
pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'master']],
                 userRemoteConfigs: [[
                    url: 'git@github.com:arjundevop/pipeline.git',
                    credentialsId: '',
                 ]]
                ])
            }
    
    stage('build') {
      steps {
        sh 'mvn -version'
        sh 'mvn clean install'
    
      }
    }
   }
  }
