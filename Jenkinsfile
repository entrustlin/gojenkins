podTemplate(containers: [
    containerTemplate(name: 'golang', image: 'golang:1.8.0', ttyEnabled: true, command: 'cat')
  ]) {
      
    node(POD_LABEL) {
        stage("versions") {
            echo "hello world"
        }
        stage("test-go") {
        }
        stage("test-docker") {
        }
        stage("test-dc") {
        }

    }
}