pipeline {
    agent any
    stages {
        stage('My-JenkinsBuild-Steps') {
            steps {
               echo "Start"
               echo "Doing something.."
               echo "End"
            }
        }
    }
    post {
        success {
            bat 'curl -s -X POST https://api.telegram.org/bot5698947661:AAFmFW1PEUa7STMd6yXq9x91tJ2oyavqKAE/sendMessage -d chat_id=-746480341 -d text="%JOB_NAME% BUILD %BUILD_ID% finish with SUCCESS"'
        }
        failure {
            bat 'curl -s -X POST https://api.telegram.org/bot5698947661:AAFmFW1PEUa7STMd6yXq9x91tJ2oyavqKAE/sendMessage -d chat_id=-746480341 -d text="%JOB_NAME% BUILD %BUILD_ID% finish with FAIL"'
        }
    }
}
