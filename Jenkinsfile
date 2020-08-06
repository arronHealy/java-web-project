pipeline{
    
    agent any
    
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'b074e091-6b28-444a-af62-5e67647cd62b', 
                path: '', 
                url: 'http://ec2-34-241-152-80.eu-west-1.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
        }
    }
}
