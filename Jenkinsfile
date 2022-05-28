node{
    stage('Clone') {
        checkout scm
    }
    stage('Ansible') {
      ansiblePlaybook (
          colorized: true,          
          playbook: 'playbook.yml',
          inventory: 'hosts.yml'
      )
    }
    stage('SSH') {
        sh "echo \"192.168.56.104 app-salaire.simplice.form\" > /etc/hosts"
        sh "curl app-salaire.simplice.form"
    }
}
