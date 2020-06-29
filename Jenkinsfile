pipeline {
    agent any 
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello world"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }, 
        stage('Upload to AWS.') {
            steps {
                retry(3){
                    withAWS(region:'us-west-2', credentials:'aws-static'){
                    s3Upload(file:'index.html', bucket:'udacityjenkinsdeploy', path:'')
                }     

            }

        }
    }

}