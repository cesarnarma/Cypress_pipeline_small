pipeline {
    agent none

    tools {
        nodejs 'Node'  // Este bloque debe estar DENTRO de `pipeline {}` y AFUERA de los `stages`
    }

    stages {
        stage('Suit de Pruebas en Paralelo') {
            parallel {
                stage('Slave 1') {
                    agent {
                        label 'Agente1_1'
                    }
                    steps {
                        git url: 'https://github.com/cesarnarma/Cypress_pipeline_small.git'
                        bat 'npm install'
                      //bat 'npm update'
                        bat 'npx cypress run --record --key 441a5d57-560f-45eb-932d-66c142f59fdd --parallel'
                    }
                }
                stage('Slave 2') {
                    agent {
                        label 'Agente1_2'
                    }
                    steps {
                        git url: 'https://github.com/cesarnarma/Cypress_pipeline_small.git'
                        bat 'npm install'
                      //bat 'npm update'
                        bat 'npx cypress run --record --key 441a5d57-560f-45eb-932d-66c142f59fdd --parallel'
                    }
                }
           /*     stage('Slave 3') {
                    agent {
                        label 'Agente1_3'
                    }
                    steps {
                        git url: 'https://github.com/cesarnarma/Cypress_pipeline_small.git'
                        bat 'npm install'
                        bat 'npm update'
                        bat 'npx cypress run --record --key c805aa5e-810c-487a-85e5-98f6f18e8294 --parallel'
                    }
                }
                stage('Slave 4') {
                    agent {
                        label 'Agente1_4'
                    }
                    steps {
                        git url: 'https://github.com/cesarnarma/Cypress_pipeline_small.git'
                        bat 'npm install'
                        bat 'npm update'
                        bat 'npx cypress run --record --key c805aa5e-810c-487a-85e5-98f6f18e8294 --parallel'
                    }
                }*/
            }
        }
    }
}
