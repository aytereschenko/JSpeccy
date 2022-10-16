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
                sh "printenv | sort"
                echo '---------------------------------------'
                echo "pwd: $PWD"
                echo '---------------------------------------'
                sh "ls -alF"
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
