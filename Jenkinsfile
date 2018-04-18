node {
  checkout scm
  stage 'Deploy application release'
  writeFile file: 'extras.json', text: 
"{'image_tag':'${IMAGE_TAG}','ecs_tasks':[${TASKS}]}"
   sh 'ansible-playbook site.yml --vault-password-file ${VAULT_PASSWORD} -e "@extras.json"'
}
