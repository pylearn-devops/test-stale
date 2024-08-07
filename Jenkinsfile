pipeline {
    agent any
    stages {
        stage('Parallel Stage 1') {
            parallel {
                stage('Run Tests 1-25') {
                    steps {
                        script {
                            // Run tests in parallel
                            def tasks = [:]
                            for (int i = 0; i < 25; i++) {
                                def index = i
                                tasks["Test${index}"] = {
                                    sh "behavex --processes 1 --parallel-id ${index}"
                                }
                            }
                            parallel tasks
                        }
                    }
                }
            }
        }
        stage('Parallel Stage 2') {
            parallel {
                stage('Run Tests 26-50') {
                    steps {
                        script {
                            // Run tests in parallel
                            def tasks = [:]
                            for (int i = 25; i < 50; i++) {
                                def index = i
                                tasks["Test${index}"] = {
                                    sh "behavex --processes 1 --parallel-id ${index}"
                                }
                            }
                            parallel tasks
                        }
                    }
                }
            }
        }
    }
}