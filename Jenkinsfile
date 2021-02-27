node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("sandhyasubudhi1998/jenkins-trigger-app")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}