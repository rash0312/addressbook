pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "MyMavenInstallation"
    }

    stages {
        stage('Compile') 
        {
            steps {
                script{
                    echo "Compiling"
                    // Run Maven on a Unix agent.
                    sh "mvn compile"
                    }
                    // Get some code from a GitHub repository
                    //git 'https://github.com/rash0312/addressbook.git/'              

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }        
        stage("Test")
        {
            steps
            {
                script{
                        echo "Building the TC"
                    sh "mvn test"
                    }
            }
        }
        stage("Package")
        {
            steps
            {
                script
                {
                    echo "Building the TC"
                    sh "mvn package"
                }
            }
        }
    }
}
