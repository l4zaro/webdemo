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
            publishHTML (target : [allowMissing: false,
                         alwaysLinkToLastBuild: true,
                         keepAll: false,
                         reportDir: 'build/reports/tests/test',
                         reportFiles: 'index.html',
                         reportName: 'Test Report',
                         reportTitles: 'WebDemo Report'])
        }
    }
}
