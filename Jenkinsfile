pipeline{
    agent any
 stages {
        stage('clone repo') {
            steps {
                git branch: 'master',
                git 'https://github.com/kpradeep710/maven-web-app.git'
            }
        }

        stage('Build') {
            steps {
                echo "build the maven project"
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                echo "connected to ec2-instance and ready to deploy"
                sh 'scp -i C:/Documents/nani.pem target/01-maven-web-app.war ec2-user@13.233.29.111:/home/ec2-user/slavenode'
            }
        }
    }
}
