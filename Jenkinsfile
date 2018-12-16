pipeline {
    agent { label 'master' }
    stages {
        stage('step1') {
            steps {
                echo "creating build output location"
                sh "mkdir -p /tmp/output"
            }
        }
        stage('step2') {
            steps {
                echo "creating files on destination location"
                writeFile file: "/tmp/output/usefulfile.txt", text: "This file is useful, need to archive it."
            }
        } 
         stage('step3') {
            steps {
                echo "compress the files"
                sh 'tar cvf /tmp/output.tar /tmp/output/usefulfile.txt'
            }
        }  
        stage('step4') {
            steps {
                echo "checking disk space"
                sh 'df -h'
            }
        } 
        stage('step5') {
            steps {
                echo "checking free mem space"
                sh 'free -m'
            }
        } 
    }
}
