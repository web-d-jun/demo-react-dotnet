pipeline {
    agent any

    stages {

        stage('Frontend Build') {

            steps {

                dir('D:\\dev\\my-project\\Frontend\\demo-react') {

                    bat 'npm install'
                    bat 'npm run build'

                }
            }
        }
    }
}