// CODE_CHANGES = getGitCodeChanges()

pipeline {
    agent any
    environment {
        VERSION = '1.0'
        GITHUB_CREDENTIALS = credentials('GitHub');
    }
    stages {
        stage("build") {
            // when {
            //     expression {
            //         env.BRANCH_NAME == "master" && env.CODE_CHANGES == true
            //     }
            // }
            steps {
                echo "Building1... ${VERSION}"  // THIS IS OK
                echo 'Building2... ${VERSION}'  // THIS IS NOT OK
            }
        }

        stage("test") {
            // when {
            //     expression {
            //         env.BRANCH_NAME == "master" || env.BRANCH_NAME == "dev"
            //     }
            // }
            steps {
                echo "Testing..."
            }
        }

        stage("deploy") {
            steps {
                withCredentials([
                    usernamePassword(
                        credentialsId: 'GitHub', 
                        usernameVariable: 'USERNAME', 
                        passwordVariable: 'PASSWORD')
                ]) {
                    echo "USERNAME = ${USERNAME}"
                }
                echo "Deploying...${USERNAME}"
            }
        }
    }

    // post {
    //     always {
    //         // will execute always wether it is a success or a failure
    //     }

    //     success {
    //         // will execute on success
    //     }

    //     failure {
    //         // will execute on failure
    //     }
    // }
}