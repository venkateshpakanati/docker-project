def label = "mypod-${UUID.randomUUID().toString()}"
images = [node:"node:9", nodeMemLmt:"1000Mi", nodeCpuLmt:"700m"]
podTemplate(label: label) {
    node(label) {
        stage('Run shell') {
            sh 'echo hello world'
        }
    }
}
