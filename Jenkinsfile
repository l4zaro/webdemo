pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew clean test --no-daemon'
            }
        }
        stage('Archive') {
            steps {
                echo 'Generating and archiving artifacts'
                sh './gradlew zip --no-daemon'
                archiveArtifacts artifacts: 'dist/webdemo.zip'
            }
        }
    }
}
