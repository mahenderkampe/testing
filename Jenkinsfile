pipeline {
    agent any
    stages{
        stage (git){
            steps{
                git branch: 'month', url: 'https://github.com/kampemahender122/testing.git'
            }
        }
        stage (build){
            steps {
                sh 'mvn clean package'
            }
        }
        stage(deploy){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'lavanya', path: '', url: 'http://15.206.69.68:8080/')], contextPath: 'ramya', war: '**/*.war'
            }
        }
    }
}
