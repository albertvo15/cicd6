pipeline {
    agent none

    stages {
        stage("build and deploy on Windows and Linux") {
            parallel {
                stage("windows parallel") {
                    agent {
                        label "windows"
                    }
                    stages {
                        stage("build") {
                            steps {
//                                bat "run-build.bat"
                                echo "run-build.bat"
                            }
                        }
                        stage("deploy") {
                            when {
                                branch "master"
                            }
                            steps {
//                                bat "run-deploy.bat"
                                echo "run-deploy.bat"
                            }
                        }
                    }
                }

                stage("linux") {
                    agent {
                        label "linux"
                    }
                    stages {
                        stage("build") {
                            steps {
//                                sh "./run-build.sh"
                                echo "./run-build.sh"
                            }
                        }
                        stage("deploy") {
                             when {
                                 branch "master"
                             }
                             steps {
//                                sh "./run-deploy.sh"
                                echo "./run-deploy.sh"
                            }
                        }
                    }
                }
            }
        }
    }
}
