pipeline {
    agent {
        node{
            label 'maven'
        }
    }
    environment {
        PATH = "/usr/share/maven/bin:$PATH"
        SONAR_TOKEN = 'sonar-cred'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('Sonar-qube analysis') {
             steps {
                withSonarQubeEnv('sonarqube-server') { // Replace 'SonarQube' with your SonarQube configuration name in Jenkins
                    sh "mvn sonar:sonar -Dsonar.token=${env.SONAR_TOKEN}"
                }
            }
        }
        
    }
}
