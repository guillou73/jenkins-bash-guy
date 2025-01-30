pipeline {
    agent any

    stages {
        stage('System Information') {
            steps {
                script {
                    sh '''
                    echo "System Information:"
                    echo "-------------------"
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

        stage('File and Directory Management') {
            steps {
                script {
                    sh '''
                    echo "File and Directory Management:"
                    echo "-----------------------------"
                    echo "Files in /tmp/mytempdir:"
                    ls -l "/tmp/mytempdir"

                    echo "Disk usage of /tmp/mytempdir:"
                    du -sh "/tmp/mytempdir"
                    '''
                }
            }
        }

        stage('Process Management') {
            steps {
                script {
                    sh '''
                    echo "Process Management:"
                    echo "--------------------"
                    ps aux | head -n 10
                    echo "Listing first 10 running processes..."
                    '''
                }
            }
        }

        stage('User and Group Management') {
            steps {
                script {
                    sh '''
                    echo "User and Group Management:"
                    echo "--------------------------"
                    echo "Current user groups: $(groups)"
                    '''
                }
            }
        }

        stage('Networking') {
            steps {
                script {
                    sh '''
                    echo "Networking:"
                    echo "-----------"
                    echo "Network Interfaces:"
                    ip addr

                    echo "Listening Network Sockets:"
                    netstat -lntp | head -n 10
                    '''
                }
            }
        }

        stage('System Resources') {
            steps {
                script {
                    sh '''
                    echo "System Resources:"
                    echo "------------------"
                    df -h
                    free -h
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
