node{
    stage('Clone') {
        checkout scm
    }
    stage('SSH') {
        sh "echo \"192.168.56.104 app-salaire.simplice.form\" > /etc/hosts"
    }
    stage('Ansible') {
      ansiblePlaybook (
          colorized: true,          
          playbook: 'playbook.yml',
          inventory: 'hosts.yml'
      )
    }
}
