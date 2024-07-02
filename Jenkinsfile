pipeline {
  agent {
    docker {
      image 'golang:1.23'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'make fmt'
        sh 'make lint'
        sh 'TAGS="bindata sqlite sqlite_unlock_notify" make test'
        sh 'TAGS="bindata sqlite sqlite_unlock_notify" make build'
        sh 'TAGS="bindata sqlite sqlite_unlock_notify" make test-sqlite'
      }
    }

  }
}