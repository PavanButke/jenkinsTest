pipeline {
    agent any

       tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "myMaven"
    }


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
