node {
    stage('Checkout') {
        checkout scm
    }

    stage('Parallel Build & Test') {
        parallel(
            'Build': {
                node {
                    sh 'echo "Building the project..."'
                }
                   
            },
            'Unit Tests': {
                node {
                    sh 'echo "Running unit tests..."'
                }
            },
            'Static Analysis': {
                node {
                    sh 'echo "Performing static code analysis..."'
                }
            }
        )
    }

    stage('Deploy') {
        sh 'echo "Deploying to production..."'
    }

    stage('Cleanup') {
        sh 'echo "Cleaning up workspace..."'
        deleteDir()
    }
}
