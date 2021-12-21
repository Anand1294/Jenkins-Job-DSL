println "URL: ${gitUrl}"
def location = (gitUrl =~ /https:\/\/[^\/]+\/[^\/]+\/([^.]+)(.git)?/)[0][1]
println "Location : ${location}"

pipelineJob (location) {
  definition {
    cpsScm {
      lightweight()
      scm {
        github('Anand1294/${location}', 'main')
      	  }
      	scriptPath('jenkinsfile')
    }
  }
  triggers {
    githubPush()
  }
}
