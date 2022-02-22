pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vsrekul5/project4.git']]])
            }
        }
        stage('Deploy-Dev'){
            sshagent(['my-app-dev']) {
                input 'Deploy  to Dev?'
                def sshCmd = 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.18.198'
                def dockerRun = 'docker run -d -p 8080:8080 --name my-app kammana/my-app:0.0.1'
                sh "${sshCmd} ${dockerRun}"
            }
        }
        stage('one'){
            steps{
                
            }            
        }
        stage('two'){
            steps{
                
            }            
        }
        stage('three'){
            steps{
                
            }            
        }
    }
}
