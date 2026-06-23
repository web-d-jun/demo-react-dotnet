pipeline {
    agent any

    stages {

        stage('Frontend Build') {

            steps {

                dir('D:\\dev\\my-project\\Frontend\\demo-react') {

                    sh 'npm install'
                    sh 'npm run build'

                }
            }
        }
    }
}