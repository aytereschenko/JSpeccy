pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo '---------------------------------------'
                sh 'printenv'
                echo '---------------------------------------'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
    }
}
