pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {

                git url: 'https://github.com/devp01/todo-app.git',
                    branch: 'main'

            }

        }

        stage('Build') {

            steps {

                sh '''
                mkdir -p build

                cp index.html build/

                cp style.css build/

                cp script.js build/
                '''

            }

        }

        stage('Test') {

            steps {

                sh '''

                test -f build/index.html

                test -f build/style.css

                test -f build/script.js

                '''

            }

        }

        stage('Deploy') {

            steps {

                sh '''

                cp -r build/* /var/www/html/todo/

                '''

            }

        }

    }

}
