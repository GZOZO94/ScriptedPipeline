properties([
    parameters([
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Build version'),
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy?'),
        choice(name: 'ENV', choices: ['dev', 'test', 'prod'], description: 'Environment')
    ])
])

node {
    stage('Checkout') {
        checkout scm
    }

    stage('Parallel Build & Test') {
        parallel(
            'Build': {
                node {
                    sh 'echo  ${params.VERSION}'
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
