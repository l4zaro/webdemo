pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew clean test'
            }
        }
        stage('Archive') {
            steps {
                echo 'Generating and archiving artifacts'
                sh './gradlew zip'
                archiveArtifacts artifacts: 'dist/webdemo.zip'
            }
        }
    }
}
