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
        stage('Pass Variable to PowerShell') {
            steps {
                powershell """
                $jenkinsVar = '${ENVIRONMENT}'
                Write-Host "The variable from Jenkins is: $jenkinsVar"
                """
            }
        }
        stage('Web') {
            steps {
                powershell """

                # Install Mustache templating engine
                Install-Module -Name PSMustache -Force

                # Load index.html template
                $template2 = 'Web/index.html'
                """
            }
        }
    }
}