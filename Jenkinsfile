pipeline{
    agent any
    
    stages {
        stage('continuous download') {
            steps {
                git 'https://github.com/mohan0306/game-of-life.git'
            }
               
        }
        stage('continuous build') {
            steps {
                sh 'mvn package'
            }
            }
            stage('continuous deploy') {
            steps {
                sh 'cp .jenkins/workspace/GOL@2/gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.63/webapps'
            }
               
            }
        stage('continuous Deliver on prod') {
            steps {
                sh 'ansible-playbook playbook1.yml  -b '
            }
        }
    }
   
}
