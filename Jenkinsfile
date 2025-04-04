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
                echo 'Test Step: Running pytest'

                # Initializing Conda properly
                source ~/miniconda3/etc/profile.d/conda.sh

                # Activating the Conda environment (replace 'mlip' with your environment name)
                conda activate mlip

                # Ensuring pytest is installed
                conda install -y pytest

                # Running pytest
                pytest

                echo 'pytest completed successfully'
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
