node {

    stage('Start'){
        checkout scm
    }
    stage('Docker Image Build & Push'){
        docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

            def customImage = docker.build("sandhyasubudhi1998/jenkins-trigger-web")

            /* Push the container to the custom Registry */
            customImage.push()
        }
    }
    stage('Deploy'){

        //sh "ansible-playbook deploytohost.yml"
        ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'ansible-2.9.6', inventory: 'dev.inv', playbook: 'deploytohost.yml'
    }
    stage('Complete'){

        sh "echo 'Build Successful'"
    }
}
