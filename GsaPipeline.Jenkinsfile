node {
    stage('Checkout') {
        checkout scm
    }

    stage('Parallel Build & Test') {
        parallel(
            'Build': {
                stage('Build') {
                    sh 'mvn clean package'
                }
            },
            'Unit Tests': {
                stage('Unit Tests') {
                    sh 'mvn test'
                }
            },
            'Static Analysis': {
                stage('Static Analysis') {
                    sh 'mvn checkstyle:check'
                }
            }
        )
    }

    stage('Deploy') {
        if (env.BRANCH_NAME == 'trunk') {
            stage('Production Deploy') {
                sh './deploy-prod.sh'
            }
        }
    }
}
