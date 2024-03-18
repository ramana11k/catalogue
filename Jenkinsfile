pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }

     environment { 
        packageVersion = ''
    }

    options {
        ansiColor('xterm')
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds() //It wont allow two builds at a time
    }


    // parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    // }
   

   
    //BUILD
    stages {       
        
        stage('Get the version') {
            steps {
                script {
                    def packageJson = readJSON file: 'package.json'
                    packageVersion = packageJson.version
                    echo "application version: ${packageVersion}"
                }
                    
            }
        }

        stage('Install dependencies') {
            steps {
                script {
                    sh """
                        npm install
                    """
                }
                    
            }
        }
                
        stage('Build') {
            steps {
                sh """
                    ls -la
                """
            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo "Here  I wrote shell script"        
                    # sleep 10            
                """
            }
        }

    }
    // POST BUILD
    post { 
        always { 
            echo 'I will always say Hello again!'
        }

        failure { 
            echo 'this runs when pipeline is failed, used generally to send alerts'
        }
        success { 
            echo 'I will always say Hello when pipeline is success'
        }
    }
}