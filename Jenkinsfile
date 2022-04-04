pipeline {
  agent any
  stages {
    stage('prepare') {
      agent any
      steps {
        git(url: 'https://github.com/bkoj-arch/JavaJunitWar.git', branch: 'main')
        tool(name: 'openjdk-8-openjdk', type: 'openjdk-8-openjdk')
      }
    }

    stage('build') {
      steps {
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