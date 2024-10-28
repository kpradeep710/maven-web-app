pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                echo "Clone the Git repository"
                git branch: 'master', url: 'https://github.com/kpradeep710/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
                echo "Build the Maven project"
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                echo "Connected to EC2 instance and ready to deploy"
                sh 'scp -i "/c/Documents/k.pradeepkumar.pem" target/01-maven-web-app.war ec2-user@3.110.216.127:/home/ec2-user/'
            }
        }
    }
}
