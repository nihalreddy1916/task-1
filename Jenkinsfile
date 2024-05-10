import groovy.json.JsonSlurper
import java.net.URL

def apiUrl = "https://api.github.com/repos/nihalreddy1916/task-1/branches"
def branches = fetchGitHubData(apiUrl)

def getBranches() {
    return branches.collect { it.name }
}

def getCommitIDs(String branch, String searchQuery) {
    def commitUrl = "https://api.github.com/repos/nihalreddy1916/task-1/commits?sha=$branch"
    def commits = fetchGitHubData(commitUrl)
    // Filter commit IDs based on the search query
    def commitIDs = commits.collect { it.sha }
    commitIDs = commitIDs.findAll { it.startsWith(searchQuery) }
    return commitIDs
}

def fetchGitHubData(String apiUrl) {
    def json = new JsonSlurper().parseText(new URL(apiUrl).text)
    return json
}

return getBranches()
