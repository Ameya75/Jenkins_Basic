pipeline {
    agent none
    stages {
        stage('Test Deploy') {
            agent { label 'test' }
            when { branch 'develop' }
            steps {
                git branch: 'develop',
                    url: 'https://github.com/Ameya75/Jenkins_Basic.git'
                sh 'mkdir -p /home/ubuntu/test-deploy'
                sh 'cp -r * /home/ubuntu/test-deploy/'
            }
        }
        stage('Prod Deploy') {
            agent { label 'prod' }
            when { branch 'main' }
            steps {
                git branch: 'main',
                    url: 'https://github.com/Ameya75/Jenkins_Basic.git'
                sh 'mkdir -p /home/ubuntu/prod-deploy'
                sh 'cp -r * /home/ubuntu/prod-deploy/'
            }
        }
    }
}
