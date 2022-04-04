pipeline {
  agent any
  stages {
    stage('prepare') {
      agent any
      steps {
        git(url: 'https://github.com/bkoj-arch/JavaJunitWar.git', branch: 'main')
        tool(name: 'jdk8', type: 'jdk')
      }
    }

    stage('build') {
      steps {
        sh 'mvn -v'
        sh 'mvn clean install'
      }
    }

    stage('test') {
      steps {
        junit 'target/surefire-reports/TEST-*.xml'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo deploy'
      }
    }

  }
}