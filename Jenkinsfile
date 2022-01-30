pipeline{
    agent any
    
    stages {
        stage('continuous download') {
            steps {
                git 'https://github.com/prasadvekhande07/game-of-life.git'
            }
               
        }
        stage('continuous build') {
            steps {
                sh 'mvn package'
            }
            }
            stage('continuous deploy') {
            steps {
                sh 'cp /mnt/JENKINS/workspace/pipeline/gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.56/webapps'
            }
               
            }
        stage('continuous Deliver on prod') {
            steps {
                sh 'ansible-playbook playbook1.yml  -b '
            }
        }
    }
   
}
