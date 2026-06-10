pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage("Build"){
            steps{
                sh '''
                mvn clean package 
                '''
            }
        }
        stage("Copy"){
            steps{
                sh '''
                cp target/*.war  /root/tomcat/webapps
                '''
            }
        }
        stage("Run"){
            steps{
                sh '''
               /root/tomcat/bin/startup.sh
                '''
            }
        }
    }
}