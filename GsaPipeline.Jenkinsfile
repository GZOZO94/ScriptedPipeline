node {

    stage('Build') {
        sh 'echo "Building the project..."'
        // Add your build commands here
    }

    stage('Test') {
        sh 'echo "Running tests..."'
        // Add your test commands here
    }

    stage('Deploy') {
        sh 'echo "Deploying the project..."'
        // Add your deploy commands here
    }

    parallel {
        stage('Static Analysis') {
            sh 'echo "Running static analysis..."'
            // Add your static analysis commands here
        }
        stage('Code Coverage') {
            sh 'echo "Calculating code coverage..."'
            // Add your code coverage commands here
        }
    }
}