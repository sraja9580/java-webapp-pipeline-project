pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'c079ca13-7ca8-4166-9157-799239eed1cf', path: '', url: 'http://ec2-3-21-154-148.us-east-2.compute.amazonaws.com:8090')], contextPath: 'java-webapp-pipeline', war: '**/java-webapp-pipeline-project.war'
            }
        }
    }
}
