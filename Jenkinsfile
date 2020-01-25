pipeline {
    agent any
    states {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-east-2', credentials:'aws-static') {
                    s3Upload(file:'index.html', bucket:'jenkins-devop-bucket')

                }
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps work too"
                    ls -lah
                '''
            }
        }
    }
}