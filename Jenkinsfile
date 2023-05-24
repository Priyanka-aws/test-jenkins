pipeline {
  agent {
    label "docker"
  }
  stages {
    stage("build") {
      agent {
        docker {
          image 'node:8.9.1'
          args '-p 3000:3000 -v $(pwd):/app'
        }
      }
      steps {
        sh "npm install"
        sh "npm run-script build"
      }
    }
    stage("test") {
      agent {
        docker {
          image 'node:8.9.1'
          args '-p 3000:3000 -v $(pwd):/app'
        }
      }
      steps {
        sh "npm test"
      }
    }
    stage("deploy") {
      agent {
        docker {
          image 'nginx:alpine'
          args '-v $(pwd)/dist:/usr/share/nginx/html'
        }
      }
      steps {
        sh "cp -r dist /usr/share/nginx/html/"
      }
      steps {
        sh "cp -r dist /usr/share/nginx/html/"
      }
    }
  }
}
