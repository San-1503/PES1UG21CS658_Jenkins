pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file
                    build 'PES1UG21CS658-1'
                    sh 'g++ -o main/test main/hello.cpp'
                    echo 'build done'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file
                    sh './main/test'
                    echo 'test done'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the executable to a directory (example)
                    sh 'mkdir -p deploy_directory'
                    sh 'main/test deploy_directory/'
                    echo 'deployment done'
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
