pipeline {
  agent any
  triggers {
    pollSCM('*/5 * * * *')
  }
  stages{
       stage ('Build'){
        steps {
          sh 'mvn clean package'
        }
         post {
           success {
             echo 'Archiving...'
             archiveArtifacts artifacts: '**/target/*war'
           }
         }
         stages ('New job') {
           steps {
             build job: 'package'
           }
         }
       }
         }
       }
  
