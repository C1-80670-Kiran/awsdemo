pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t kirandada0303723/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_T27Taos6Hn5T7R_Nvs0UkQ9lUDQ | /usr/bin/docker login -u kirandada0303723 --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push kirandada0303723/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image kirandada0303723/jenkinsdemo --force myservice'
            }
        }

    }
}
