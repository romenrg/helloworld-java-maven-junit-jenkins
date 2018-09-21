pipeline {
    agent any
    tools {
        maven 'Maven 3.3.9'
        jdk 'jdk8'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
        stage ('Build') {
            sh 'mvn install'
        }
        stage('Results') {
            junit 'target/surefire-reports/**/*.xml'
            archive 'target/*.jar'
        }
    }
}