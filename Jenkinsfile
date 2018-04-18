node {
  checkout scm
  stage 'Deploy application release'
  writeFile file: 'password.txt', text:
"{'${VAULT_PASSWORD}'}"
  writeFile file: 'extras.json', text: 
"{'image_tag':'${IMAGE_TAG}','ecs_tasks':[${TASKS}]}"
   sh 'ansible-playbook site.yml --vault-password-file @password.txt -e "@extras.json"'
}
