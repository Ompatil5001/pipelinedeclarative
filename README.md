

  pipeline {

    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url:'https://github.com/Ompatil5001/pipelinescripted.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                bat "xcopy /Y /I /E /F /C *.html C:\\xampp\\htdocs\\"
            }
        }
    }
}
