node("docker") {
    docker.withRegistry('serafettinkaratas/myrepo', 'serafettinkaratas') {
    
        git url: "https://github.com/serafettinserafettin/docker-base-tester-behat.git", credentialsId: 'serafettinserafettin'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
    
        stage "build"
        def app = docker.build "my-project"
    
        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}
