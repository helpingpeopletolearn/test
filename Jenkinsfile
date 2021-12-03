pipeline {
  agent any
  stages {
    stage('Fetch code from git') {
      steps {
        git(url: 'https://github.com/helpingpeopletolearn/test.git', branch: 'main', poll: true)
      }
    }

    stage('Install and start apace') {
      steps {
        sh '''sudo apt-get install apache2 -y
sudo service apache2 start'''
      }
    }

    stage('Deploy code to apache') {
      steps {
        sh 'sudo cp -R * /var/www/html/'
      }
    }

  }
}