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
                deploy adapters: [tomcat7(credentialsId: '18e3a2f3-dae5-4a2a-8baa-3d063e1b48fe', path: '', url: 'http://ec2-3-250-97-139.eu-west-1.compute.amazonaws.com:8080/')], contextPath: 'javawebproject', war: '**/java-web-project.war'
            }
        }
    }
}
