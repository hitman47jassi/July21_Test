pipeline {
    agent any

    
    
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
             environment {
                 def TMP_FILENAME = "";
                 FILES_DIR = '/var/lib/jenkins/workspace/Folder_1/ReadListofFiles/Folder_1'
                 //def filenames = readFile(TMP_FILENAME).split( "\\r?\\n" );
                
            }
             
             
            steps {
                echo 'Reading files'
                echo 'Path is ${FILES_DIR}'
                //def TMP_FILENAME = "";
                sh "pwd"
                sh "cd ${FILES_DIR}"
                sh 'ls -alrt'
                //sh "ls ${FILES_DIR} > ${TMP_FILENAME}"
                
              
              
                   
              
                //def filenames = readFile(TMP_FILENAME).split( "\\r?\\n" );
                //sh "rm -f ${TMP_FILENAME}"

                //for (int i = 0; i < filenames.size(); i++) {
                //def filename = filenames[i];
                //echo "${filename}"
                //}
                
                echo '--------------------------------------------------------'
            }
        }
    }
}
