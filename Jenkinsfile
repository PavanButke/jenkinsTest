pipeline {
    agent any



    stages {
       
        
         stage('Build') {
            steps {
               bat 'mvn clean package'
            }
        }
        

         stage('Deploy') {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'new-cred', path: '', 
               url: 'http://localhost:9099/')], contextPath: null, 
               onFailure: false, war: '**/*.war'
            }
        }
        
        
    }
}
