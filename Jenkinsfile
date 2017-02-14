node("docker") {
    docker.withRegistry('serafettinkaratas/myrepo', 'serafettinkaratas') {
    
        git url: "<<your-git-repo-url>>", credentialsId: 'serafettinserafettin'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
    
        stage "build"
        def app = docker.build "your-project-name"
    
        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}
