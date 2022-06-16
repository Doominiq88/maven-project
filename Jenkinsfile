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
       }

           stage ('1') {
             steps {
               sh "cp **/target/*.war /home/ivan/programms/tomcat-prod/webapps"
             }     
           }
         }
       }
    
} 
  
