pipeline {
    agent any

    options {
        ansiColor('xterm')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo '---------------------------------------'
                sh 'printenv | sort'
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
