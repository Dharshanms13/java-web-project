pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '7925e771-b388-4f22-98cd-f3a0200c6008', path: '', 
                url: 'http://ec2-54-172-70-135.compute-1.amazonaws.com:8080/')], 
                    contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
