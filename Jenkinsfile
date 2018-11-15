/*
pipeline {
    agent any 
    /-
    tools {
        maven 'Mavent TEST'
    }
    -/
    stages {
        stage ('Build') {
            steps {
                echo ' Build.'
                sh 'mvn compile'
                /-
                sh '/usr/bin/git config remote.origin.url https://github.com/IvanciniGT/maven-test-repository'
                -/
            }
        }
        stage ('Test') {
            steps {
                echo ' Test.'
                sh 'mvn test'
            }
        }
        stage ('Deploy') {
            steps {
                echo ' Deploy.'
            }
        }
    }
}
*/

node {
    checkout scm
    stage ( 'Buid') {
        /* echo 'Build ...' */
        withMaven( maven:'Mavent TEST' ) {
             sh 'mvn compile'
        }
    }
    stage ( 'Test') {
        /* echo 'Test ...'*/
        withMaven( maven:'Mavent TEST' ) {
             sh 'mvn test'
        }
    }
    stage ( 'Deploying') {
        /* echo 'Dploying ...'*/
        withMaven( maven:'Mavent TEST' ) {
             sh 'mvn package'
           deletedir() 
        }
        /* sh 'rm -rf ${WORKSPACE}' */
    }
}
