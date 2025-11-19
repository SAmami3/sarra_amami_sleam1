pipeline {
    agent any

    environment {
        M2_HOME = '/usr/share/maven'
        PATH = "${M2_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Build & Package') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
    }

    post {
        success {
            echo '✅ Build réussi (tests ignorés).'
        }
        failure {
            echo '❌ Build cassé, va voir les logs.'
        }
    }
}
