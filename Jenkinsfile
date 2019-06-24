pipeline{
  agent any
  stages {
    stage('Test'){
      steps {
        script {
          try {


            env.NODE_ENV = "test"

            print "Environment will be : ${env.NODE_ENV}"

            sh 'node -v'
            sh 'npm prune'
            sh 'npm install'
            sh 'npm test'
          }
          catch (e) {
            throw e
          }
        }
      }
    }

    stage('Cleanup'){
      steps {
        script {
          try {


            echo 'prune and cleanup'
            sh 'npm prune'
            sh 'rm node_modules -rf'


          }
          catch (e) {
            throw e
          }
        }
      }

    }
  }
}
