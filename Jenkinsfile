/*def label = "mypod-${UUID.randomUUID().toString()}"
images = [node:"node:9", nodeMemLmt:"1000Mi", nodeCpuLmt:"700m"]
podTemplate(label: label) {
    node(label) {
        containerTemplate {
                    name 'dind-jdk8-maven3'
                    image 'eu.gcr.io/jenkins-demo/dind-jdk8-maven3:v4'
                    ttyEnabled true
                    command 'cat'
         }
    /*    stage('Run shell') {
            sh 'echo hello world'
        }
    }
}*/

podTemplate(label: 'pod-golang', 
    containers: [
        containerTemplate(
            name: 'golang',
            image: 'golang',
            ttyEnabled: true,
            command: 'cat'
        )
    ]
) {
    node ('pod-golang') {

        stage 'Switch to Utility Container'
        container('golang') {

          sh ("go version")

        }
    }
}
