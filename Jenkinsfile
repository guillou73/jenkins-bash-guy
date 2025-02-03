pipeline {
    agent any

    stages {
        stage('System Information') {
            steps {
                script {
                    sh '''
                        echo "System Information:"
                        echo "----------------"
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

        stage('File Operations') {
            steps {
                script {
                    sh '''
                        # Create a temporary directory
                        TEMP_DIR=$(mktemp -d)
                        echo "Temporary directory created: $TEMP_DIR"

                        # Create a new file within the temporary directory
                        FILE_PATH="$TEMP_DIR/myfile.txt"
                        touch $FILE_PATH
                        echo "File created: $FILE_PATH"

                        # Write a line of text to the file
                        echo "Hello, Jenkins!" > $FILE_PATH
                        echo "Text written to file."

                        # Display the contents of the file
                        echo "Displaying file contents:"
                        cat $FILE_PATH

                        # Copy the file to another location
                        cp $FILE_PATH "$TEMP_DIR/copied_file.txt"
                        echo "File copied to: $TEMP_DIR/copied_file.txt"

                        # Move the file to a different directory
                        mv "$TEMP_DIR/copied_file.txt" "$TEMP_DIR/moved_file.txt"
                        echo "File moved to: $TEMP_DIR/moved_file.txt"

                        # Delete the original file
                        rm $FILE_PATH
                        echo "Original file deleted."

                        # Cleanup: Remove the temporary directory
                        rm -r $TEMP_DIR
                        echo "Temporary directory removed."
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
