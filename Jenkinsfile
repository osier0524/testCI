pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build stage is starting...'
                // 这里可以添加构建步骤，比如编译代码
            }
        }

        stage('SonarQube Scan') {
            steps {
                echo 'SonarQube scan is running...'
                sh 'java -version'
                sh 'echo JAVA_HOME: $JAVA_HOME'
                // 执行 SonarQube 扫描
                sh 'sonar-scanner -Dsonar.projectKey=YourProjectKey -Dsonar.sources=.' 
            }
        }

        stage('Test') {
            steps {
                echo 'Tests are running...'
                // 这里可以添加测试步骤，比如运行自动化测试
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // 这里可以添加部署步骤，比如将构建的应用程序部署到服务器
            }
        }
    }

    post {
        always {
            echo 'This will always run regardless of build result.'
        }

        success {
            echo 'Build was successful!'
        }

        failure {
            echo 'Build failed.'
        }
    }
}
