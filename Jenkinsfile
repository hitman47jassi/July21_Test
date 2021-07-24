pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World -from GIT'
            }
        }
        
        stage('COPY') {
            steps {
                echo 'Copy file from git to jenkins workspace'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/hitman47jassi/WarFile.git']]])
            }
        }
    }
}
