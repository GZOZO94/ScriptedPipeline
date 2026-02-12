node {
    stage('Checkout') {
        checkout scm
    }

    stage('Parallel Build & Test') {
        parallel(
            'Build': {
                    sh 'echo "Building the project..."'
            },
            'Unit Tests': {
                    sh 'echo "Running unit tests..."'
            },
            'Static Analysis': {
                    sh 'echo "Performing static code analysis..."'
            }
        )
    }

    stage('Deploy') {
        sh 'echo "Deploying to production..."'

    }
}
