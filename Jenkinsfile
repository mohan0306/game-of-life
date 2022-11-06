// currentBuild.displayName = "Game-of-Life-#"+currentBuild.number
// pipeline{
//     agent any
//     environment {
//         PATH = "$PATH:/root/maven/apache-maven-3.8.5"
//     }
    
//     stages {
//         stage('continuous download') {
//             steps {
//                 git 'https://github.com/mohan0306/game-of-life.git'
//             }
               
//         }
//         stage('continuous build') {
//             steps {
//                 sh 'mvn clean package'
//             }
//             }
//             stage('sonarqube analysis') {
//                 steps {
//                     withSonarQubeEnv('sonarqube-8.9.5'){
//                         sh "mvn sonar:sonar"
//                     }
//                 }
//             }
//             stage('continuous deploy') {
//             steps {
//                 sh 'cp /mnt/Jenkins_path/workspace/GOL@2/gameoflife-web/target/gameoflife.war /root/mnt/apache-tomcat-9.0.63/webapps'
//             }
               
//             }
//         stage('continuous Deliver on prod') {
//             steps {
//                 sh 'ansible-playbook playbook1.yml  -b '
//             }
//         }
//     }
   
// }


currentBuild.displayName = "Game-of-Life-#"+currentBuild.number
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
                sh 'cp /mnt/Jenkins_path/workspace/GOL@2/gameoflife-web/target/gameoflife.war /root/mnt/apache-tomcat-9.0.63/webapps'
            }
               
            }
        stage('continuous Deliver on prod') {
            steps {
                sh 'ansible-playbook playbook1.yml  -b '
            }
        }
    }
   
}
/////////////////
