{
 environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-amazon-corretto.x86_64'
        MAVEN_HOME = '/usr/share/maven'
    }
 stages {
        stage('clone repo') {
            steps {
                echo "Clone the Git repository"
                git url: 'https://github.com/kpradeep710/maven-web-app.git'
            }
        }

        stage('Build') {
            steps {
                echo "build the maven project"
                bat 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                echo "connected to ec2-instance and ready to deploy"
                bat '''
                scp -i "C:/ProgramData/Jenkins/.jenkins/workspace/TASK-2/target/01-maven-web-app.war" ec2-user@13.201.90.156:/home/ec2-user
                '''
            }
        }
    }
}
