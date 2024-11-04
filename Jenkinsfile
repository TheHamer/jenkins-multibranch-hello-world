pipeline {
    agent any
    
    tools {
        // install the maven version configured as "M3" and add it to the path
        maven "M3"
    }
    
    stages {
        stage('Checkout') {
            steps {
                // get code from github repo
                git branch: 'main', url: 'https://github.com/LahmiaHoqueQA/lbg-hello-world-maven.git'
            }
        }
        stage('Compile') {
            steps {
                // run maven on unix agent
                sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                // run tests
                sh "mvn -Dmaven.compile.skip test"
            }
        }
        stage('Package') {
            steps {
                sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
            }
        }
    }
}
