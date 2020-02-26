node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("miltonc/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
    stage('Static Code Analysis')
    {
        echo "Static Code Analysis"
    }
    stage ('Unit Testing')
    {
        echo "Unit Testing"
    }
    stage ('Build')
    {
        echo "Build"
    }
    stage ('Delivery')
    {
        echo "Delivery"
    }
    }
