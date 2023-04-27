pipeline{
    agent any
    environment{
        staging_server="3.231.252.107"
    }

    stages(
        stage('Deploy To Remote'){
        steps{
            sh 'scp ${WORKSPACE}/* root@$(staging_server):/var/www/html/'
        }
        }
    )
}
