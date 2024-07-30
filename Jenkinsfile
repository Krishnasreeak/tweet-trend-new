pipeline {
    agent {
        node{
            label 'maven'
        }
    }
    environment {
        PATH = "/usr/share/maven/bin:$PATH"
    }
      stages {
        stage('Build') {
            steps {
                sh 'mvn clean deploy -Dmaven.test.skip=true'
            }
        }
        stage('Test') {
            steps {
                echo "------------UNIT TEST STARTED-------------"
                sh 'mvn surefire-report:report'
                echo "------------UNIT TEST COMPLETED-------------"
            }
        }
    }
}
