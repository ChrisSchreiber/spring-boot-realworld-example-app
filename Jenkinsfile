pipeline {
    agent {
        label "lead-toolchain-gradle"
    }

    stages {
        stage('Test') {
            steps {
                sh './gradlew clean test --no-daemon'
            }
        }
        stage('Build') {
            steps {
                sh './gradlew clean build --no-daemon'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
