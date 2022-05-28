node{
    stage('Clone') {
        checkout scm
    }
    stage('SSH') {
        sh "echo \"192.168.131.130 app-salaire.corentin.form\" > /etc/hosts"
    }
    stage('Ansible') {
      ansiblePlaybook (
          colorized: true,          
          playbook: 'playbook.yml',
          inventory: 'hosts.yml'
      )
    }
}
