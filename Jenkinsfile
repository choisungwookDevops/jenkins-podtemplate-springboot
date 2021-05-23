def label = "mypod-${UUID.randomUUID().toString()}"
podTemplate(label: label, containers: [
    containerTemplate(name: 'maven', image: 'maven:3.6.3-openjdk-11-slim', ttyEnabled: true, command: 'cat'),
  ]) {
 
    node(label) {
        stage('Get a Maven project') {
            git url: 'https://github.com/choisungwookDevops/jenkins-podtemplate-springboot.git',
                branch: 'main'

            container('maven') {
                stage('Build a Maven project') {
                    sh 'mvn clean package'
                }
            }
        }
    }
}