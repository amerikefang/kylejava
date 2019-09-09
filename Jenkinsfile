node {
    stage('Git Check Out'){
      git 'https://github.com/amerikefang/kylejava'

    }

    stage('Maven Build'){
      def mvnHome = tool name: 'maven-3', type: 'maven'
        sh '${mvnHome}/bin/mvn clean package'
    }
    stage('Archive Artifacts'){
         archiveArtifacts 'target/myweb-8.2.0.war'
    }

    stage('Email'){
    mail bcc: '', 
         body: '''This is for testing Pipline. Thanks,Java Home''', 
         cc: '', 
         from: '', 
         replyTo: '', 
         subject: 'Pipeline Demo-jenkinsfile+git+maven', 
         to: 'amerikefang@gmail.com'
    }
}
