pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file
                    sh 'g++ -o test hello.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file
                    sh './test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the executable to a directory (example)
                    sh 'mkdir -p deploy_directory'
                    sh 'test deploy_directory/'
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
