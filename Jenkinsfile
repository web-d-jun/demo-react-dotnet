pipeline {
    agent any

    environment {
        frontend_path = "Frontend/demo-react"
        project_path  = "."
        publish_path  = "publish"
        csproj_name   = "demo-react-dotnet.csproj"
    }

    stages {
        stage('Frontend Build') {
            steps {
                dir("${frontend_path}") {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Copy React To wwwroot') {
            steps {
                sh '''
                rm -rf wwwroot
                mkdir -p wwwroot
                cp -r ${frontend_path}/dist/* wwwroot/
                '''
            }
        }

        stage('Dotnet Publish') {
            steps {
                sh '''
                rm -rf ${publish_path}
                dotnet publish ${csproj_name} -c Release -o ${publish_path}
                '''
            }
        }

        stage('Check Result') {
            steps {
                sh 'ls -al ${publish_path}'
                sh 'ls -al ${publish_path}/wwwroot'
            }
        }
    }
}