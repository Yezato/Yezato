pipeline {
  agent any
  stages {
    stage('Composer Install') {
      steps {
        sh 'composer install'
      }
    }

    stage('PHPLint') {
      steps {
        sh 'find app -name ".php" -print0 | xargs -0 -n1 php -l'
      }
    }

    stage('PHPUnit') {
      steps {
        sh 'vendor/phpunit/phpunit/phpunit --bootstrap build/bootstrap.php --configuration phpunit-coverage.xml'
      }
    }

  }
}