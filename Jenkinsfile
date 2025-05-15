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
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '51fa384f-454e-4ae6-adf6-973b48951599', path: '', 
                url: 'http://ec2-54-172-70-135.compute-1.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
