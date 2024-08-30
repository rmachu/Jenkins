pipeline{
    agent any

    stages{
        stage('Build'){
            steps{
                echo '''Involves building the code using a build automation tool to compile and package the code. 
                Examples of build automation tools are Mavern, Gradle, Apache Ant, npm and Nant'''
            }
            
        }
        stage('Unit and Integration Tests'){
            steps{
                echo '''Running tests on units and integration to ensure code works and different components behave 
                as expected when integrated together. Tools for this can be JUnit for unit tests,
                and Selenium for integration testing by incorporating the necessary plugins. TestNG can also be used 
                for both unti and integration testing.'''
            }

        }
        stage('Code Analysis'){
            steps{
                echo '''Analyse code to check if it meets industry standards. We can use PMD to do this by 
                utilising the PMD plugin.'''
            }

        }
        stage('Security Scan'){
            steps{
                echo '''A security check on the code to identify potential risks and vulnerabilities. 
                Tools used for this can be OWASP Dependency-Check by using the plugin.'''
            }

        }
        stage('Deploy to Staging'){
            steps{
                echo '''Deploy the application to a staging server to mimic the final production environment. 
                A tool we can use for this is AWS CodeDeploy that deploys to AWS EC2.'''

            }
        }

        stage('Integration Tests on Staging'){
            steps{
                echo '''Run integration tests in this staging environment to ensure application functions as expected
                in a production-like environment. A tools we can use is Selenium'''
            }

        }
        stage('Deploy to Production'){
            steps{
                echo '''Deploy the application to the final production server. Possible tools we can use for this is 
                AWS CodeDeploy or Kubernetes.'''
            }
        }
    }
     post{
            success{
                emailext(
                    to: "s223083661@deakin.edu.au",
                    subject: "Status Update",
                    body: "Build was successful",
                    attachLog: true
                )
            }
            failure{
                emailext(
                    to: "s223083661@deakin.edu.au",
                    subject: "Status Update",
                    body: "Build was unsuccessful",
                    attachLog: true
                )
            }
        }
}
