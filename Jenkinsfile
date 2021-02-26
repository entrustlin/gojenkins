podTemplate(containers: [
    containerTemplate(name: 'golang', image: 'golang:1.8.0', ttyEnabled: true, command: 'cat')
  ]) {
      
    node(POD_LABEL) {
        stage("versions") {
            sh "java -version"
            sh "docker version"
            sh "docker-compose version"
        }
        stage("test-go") {
            sh "go get -d -v -t && go test --cover -v ./... --run UnitTest && go build -v -o go-demo"
        }
        stage("test-docker") {
            sh "docker container run -v ${workspace}:/usr/src/myapp -w /usr/src/myapp golang:1.9 bash -c \"go get -d -v -t && go test --cover -v ./... --run UnitTest && go build -v -o go-demo\""
        }
        stage("test-dc") {
            sh "docker-compose run --rm unit"
        }

    }
}