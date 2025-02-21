pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'
                
                # Initialize conda (adjust the path if your conda installation is elsewhere)
                sudo /home/ruiqiy/miniconda3/bin/conda init
                
                # Run pytest using the specified conda environment (replace "myenv" with your actual environment name)
                sudo /home/ruiqiy/bin/conda run -n mlip pytest
                
                # Once confirmed working, remove the exit command below
                # exit 1
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
