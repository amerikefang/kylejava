node {
    stage('Git'){
      git 'https://github.com/amerikefang/kylejava'

    }

    stage('Maven Build'){
      def mvnHome = tool name: 'maven3', type: 'maven'
        sh '${mvnHome}/bin/mvn clean package'
    }
    stage('Archive Artifacts'){
         archiveArtifacts 'target/myweb.war'
    }

    stage('Email'){
    mail bcc: '', body: '''Thanks,
    Java Home''', cc: '', from: '', replyTo: '', subject: 'Pipeline Demo', to: 'amerikefang@gmail.com'
    }
}
