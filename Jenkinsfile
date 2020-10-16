pipeline {
    agent {
        label "lead-toolchain-gradle"
    }

    stages {
        stage('Test') {
            steps {
                container('gradle') {
                    in_toto_wrap(['stepName': 'Test',
                            'credentialId': 'intoto',
                            'transport': 'http://scribbles.ngrok.io']){
                        sh './gradlew clean test --no-daemon'
                    }
                }
            }
        }
        stage('Build') {
            steps {
                container('gradle') {
                    in_toto_wrap(['stepName': 'Build',
                            'credentialId': 'intoto',
                            'transport': 'http://scribbles.ngrok.io']){
                        sh './gradlew clean build --no-daemon'
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
