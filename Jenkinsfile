pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew clean test'
                sh 'pwd'
                sh 'll'
            }
        }
        stage('Archive') {
            steps {
                echo 'Generating and archiving artifacts'
                sh './gradlew zip'
                sh 'pwd'
                sh 'll'
                //archiveArtifacts artifacts: 'dist/webdemo.zip'
            }
        }
    }
}
