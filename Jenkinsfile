pipeline{
    agent{
        label "slave-2"
    }
    stages{
        stage("Clean Workspace"){
            steps{
                cleanWs()
            }
        }
        stage("Checkout from SCM"){
            steps{
                git branch: 'master', credentialsId: '7854c600-87b0-4c63-a9a2-1bb48ab8dd58', url: 'https://github.com/rbale3108/spring-jpa-pipeline-example.git'
            }
        }
        stage("Build Application"){
            steps{
                sh "mvn clean install"
            }
        }
        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}