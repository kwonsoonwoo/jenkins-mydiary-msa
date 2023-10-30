node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/kwonsoonwoo/jenkins-mydiary-msa.git'
    }

    stage('Build image') {
       dockerImage = docker.build("zenuine/mydiary-front:2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
