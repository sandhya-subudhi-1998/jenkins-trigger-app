node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("sandhyasubudhi1998/jenkins-trigger-app-1")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
