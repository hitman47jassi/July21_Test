def testfn(){

echo "This is a test fn"
}






pipeline {
    agent any
    
    environment {
        
        int NUM_1 = 1
        int NUM_2 = 2
        int total = 0
    }
    
    options {
        timeout(time: 1, unit: 'MINUTES')
    }
    
    
    
    stages {
        stage('Start') {
            steps {
                echo 'Hello World -from GIT'
                 echo '--------------------------------------------------------'
            }
        }
        
        stage('Copy_Workspace') {
            steps {
                echo 'Copy file from git to jenkins workspace'
                //checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/hitman47jassi/WarFile.git']]])
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/hitman47jassi/PracticeOnly.git']]])
                echo '--------------------------------------------------------'
            }
        }
         stage('Read_FileData') {
             
            steps {
                
                echo "NUM_1 is ${env.NUM_1} and CLASS is ${env.NUM_1.class}"
                ${env.total} = ${env.NUM_1} + ${env.NUM_2}
                sh 'echo THIS IS SH ECHO and total is $total'
                
                script{
                    testfn();
                }
                
                echo '--------------------------------------------------------'
            }
        }
    }
}
