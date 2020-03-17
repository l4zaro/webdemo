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
                echo 'Generating zip'
                sh './gradlew zip --no-daemon'
            }
        }
    }
    post {
        always {
            echo 'Archiving artifact'
            archiveArtifacts artifacts: 'dist/webdemo.zip'
            junit 'build/reports/tests/test/index.html'
        }
    }
}
