pipeline {
    agent any

    environment {
        ENVIRONMENT = "dev"
    }


    stages {
        stage('Prepare') {
            steps {
                script {
                    env.WEB_PAGE_NAME = "${ENVIRONMENT}.html"
                }
            }
        }
        stage('Web') {
            steps {
                powershell """

                # Install Mustache templating engine
                Install-Module -Name PSMustache -Force

                # Load index.html template
                \$template2 = 'Web/index.html'
                """
            }
        }
    }
}