pipeline {
    agent {label "sys-admin-mnf"}

    stages {
        stage('Build') {
            steps {
                echo 'build'
                withCredentials([usernamePassword(credentialsId: 'iti-sys-admin-mnf-slave-cred', passwordVariable: 'PASSWORD_SYSADMIN', usernameVariable: 'USERNAME_SYSADMIN')]){
                sh """
                    docker login -u ${USERNAME_SYSADMIN} -p ${PASSWORD_SYSADMIN}
                    docker build -t ahmedabass78/usermanagement:v1 .
                    docker push ahmedabass78/usermanagement:v1
            
                """
                } 
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
                sh "ls"
            }
        }
    }
}
