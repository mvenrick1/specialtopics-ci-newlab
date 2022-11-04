
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/mvenrick1/specialtopics-ci-newlab'
  }

  stage('Build') {
    // you should build this repo with a maven build step here
         withMaven (maven : 'maven3') {
                sh "mvn package"
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
  }
  // you should add a test report here

  stage('Test') {
          sh 'make check || true'
          junit '**/target/**/*.xml'
    }
}
