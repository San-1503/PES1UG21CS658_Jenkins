pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file
                    sh 'g++ -o main/test main/hello.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file
                    sh './main/test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the executable to a directory (example)
                    sh 'mkdir -p deploy_directory'
                    sh 'amain/test deploy_directory/'
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
