node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("bsn/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
