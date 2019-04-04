pipeline {
    agent any 

    stages {
        stage("Pre-deploy Validation"){
            when { branch 'develop'}
            steps{
                    echo "This is the build job"
                }
            }

        stage("Static Code Analysis"){
            when { branch 'develop'}
            steps {
                echo 'This job runs static code analysis'
            }
        }

        stage("Unit Testing"){
            when { branch 'develop'}
            steps {
                echo 'This job runs all unit testing'
            }
        }

        stage("Deploy to Environment"){
            steps{
                echo "This job initiates pre-deploy validation"
            }
        }

        stage("Performance Testing"){
            when { anyOf {branch 'develop'; branch 'staging'; branch 'release'} }
            steps {
                echo 'This job runs all performance testing'
            }
        }

        stage("Functional Testing"){
            steps {
                echo 'This job runs all functional testing'
            }
        }

        stage("Security Testing"){
            when { branch 'staging'}
            steps {
                echo 'This job runs all security testing'
            }
        }
    }
}
