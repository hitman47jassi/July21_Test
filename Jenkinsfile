def testfn(test){

echo "SUM = $test"
}






pipeline {
    agent any
    
    environment {
        
        int NUM_1 = "99".toInteger()
        int NUM_2 = "22".toInteger()
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
                //${env.total.toInteger()} = ${env.NUM_1.toInteger()} + ${env.NUM_2.toInteger()}
                sh 'echo THIS IS SH ECHO and total is $total'
                
                script{
                    
                    
                    env.total = env.NUM_1.toInteger() + env.NUM_2.toInteger()
                    echo "$env.total"
                    testfn(env.total);
                }
                
                echo '--------------------------------------------------------'
            }
        }
    }
}
