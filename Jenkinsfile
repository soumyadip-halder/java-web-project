pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn -Dskiptests clean package"
            }
        }
        stage("Test"){
            steps{
                sh "mvn test"
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: '452cf887-6469-4806-9fbb-58b6bfae842c', path: '', url: 'http://ec2-3-250-97-139.eu-west-1.compute.amazonaws.com:8080/')], contextPath: 'javawebproject', war: '**/java-web-project.war'
            }
        }
    }
}
