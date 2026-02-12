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
}