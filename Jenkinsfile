// CODE_CHANGES = getGitCodeChanges()

pipeline {
    agent any
    environment {
        VERSION = '1.0'
    }
    stages {
        stage("build") {
            // when {
            //     expression {
            //         env.BRANCH_NAME == "master" && env.CODE_CHANGES == true
            //     }
            // }
            steps {
                echo "Building1... ${VERSION}"
                echo 'Building2... ${VERSION}'
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
                echo "Deploying..."
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