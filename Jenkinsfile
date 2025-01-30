pipeline {
    agent any

    stages {
        stage('System Information') {
            steps {
                script {
                    sh '''
                    echo "System Information:"
                    echo "-----------------"
                    echo "Current Date and Time: $(date)"
                    echo "Hostname: $(hostname)"
                    echo "Operating System and Version:"
                    cat /etc/os-release

                    echo "System Uptime: $(uptime)"
                    echo "Current User: $(whoami)"
                    '''
                }
            }
        }
    }

    post {
        always {
            echo "Script execution completed."
        }
    }
}
