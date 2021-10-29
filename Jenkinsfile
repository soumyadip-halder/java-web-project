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
    }
}
