pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/SUdvisha/DEMO1.git'
            }
        }

        stage('Maven Build') {
            steps {
                bat "mvn clean package -DskipTests"
            }
        }

        stage('Archive JAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            echo "✅ JAR build successful!"
        }
        failure {
            echo "❌ Build failed!"
        }
    }
}
