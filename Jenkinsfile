pipeline {
    agent {
        node{
            label 'maven'
        }
    }

    stages {
        stage('git clone') {
            steps {
                git branch: 'main', credentialsId: 'git-cred', url: 'https://github.com/Krishnasreeak/tweet-trend-new.git'
            }
        }
    }
}
