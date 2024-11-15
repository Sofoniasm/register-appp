pipline {
    agent { label 'Jenkins-Agent'}
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("cleanup Workspace"){
            steps{
                cleanWs()
            }
        }
     stages{
        stage("Checkout from SCM"){
            steps{
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/Sofoniasm/registration-app.git']]) 
            }   
        }
    stages{
        stage("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }
    stages{
        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }

}