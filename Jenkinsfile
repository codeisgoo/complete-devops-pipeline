pipeline{
    agent any
    stages{
        stage("clean Workspace"){
            steps{
                cleanWs()
            }
        }
        stage("code checkout"){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/dmancloud/complete-prodcution-e2e-pipeline.git']])
            }
        }
        stage("mvn compile"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("mnv test"){
            steps{
                sh "mnv test"
            }
        }
    }
}