def run_ls(options, arguments) {
    ls = sh script:"ls ${options} ${arguments}",returnStdout:true
    echo "${ls}"
}
node('master') {
    stage('Detect') {
        timedate_start = sh script:"date",returnStdout:true
        run_ls('-l','/tmp')
    }
    stage('Build') {
        echo "test line"
    }
    stage('Configure') {
    
    }
    stage('Test') {
        echo "Run smoke tests"
        echo "Run functionality tests"
        echo "Run regression tests"
        echo "Run compatibility tests"
    }
    stage('Approval') {
    input "Please check before we push into production"
    }
    stage('Deploy') {
        echo "Update device inventory"
        echo "Add a device to monitoring tool, security center, and syslog server"
    }
    stage('Finalize') {
        timedate_end = sh script:"date",returnStdout:true
    
        //echoing the results
        sh "echo Job started at ${timedate_start}"
        sh "echo Job ended at ${timedate_end}"
    }
}
