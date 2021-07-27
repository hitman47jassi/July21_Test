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
                 FILES_DIR = 'Folder_1/ReadListofFiles'
                 //def filenames = readFile(TMP_FILENAME).split( "\\r?\\n" );
                
            }
             
             
            steps {
                echo 'Reading files'                
                //def TMP_FILENAME = "";
                sh "pwd"
                sh 'ls -alrt'
                //sh "ls ${FILES_DIR} > ${TMP_FILENAME}"
                
                script {
                  def filenames = readFile(TMP_FILENAME).split( "\\r?\\n" );
                   
                }
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
