node {

    stage('Clone') {
        
        git 'https://github.com/AshutoshM10/hello-world-1.git'
    
    }
    stage('Build') {
        
        withMaven(jdk: 'java', maven: 'maven') {
              sh ' mvn clean package'
            }
        
        
    }
    stage('Deploy') {
        deploy adapters: [tomcat9(credentialsId: 'tomcat_cred', path: '', url: 'http://13.127.90.253:8080/')], contextPath: null, war: '**/*.war'
    }
}
