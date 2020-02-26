node {

    stage('checkout scm')
    {
        docker.withRegistry('https://registry.hub.docker.com', 'bn8595') {

        def customImage = docker.build("bn8595/dockerwebapp")

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
