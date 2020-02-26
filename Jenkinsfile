node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'bn8595') {

        def customImage = docker.build("bn8595/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
