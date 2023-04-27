pipeline{
    agent any
    environment{
        staging_server="3.231.252.107"
    }

    stages{
        stage('Deploy To Remote'){
        steps{
            
            sh '''
            for fileName in 'find ${WORKSAPCE} -type f -mnin -10 | grep -v ".git"|grep -v "Jenkinsfile" '
            do 
            fil=${ echo ${fileName} | sed 's/'"${JOB_NAME}"'/ /'| awk {'print $2'} }
            scp ${WORKSPACE}/${fil} root@${staging_server}:/var/www/html/${fil}
            done
            
            '''
            
        }
        }
    }
}
