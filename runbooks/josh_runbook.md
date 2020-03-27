# josh runbook

## Verifying ECS Images

* All our images for all environments are stored on the development-admin ECR account. 
* ECS pulls the most recent images from ECR to spin up new tasks.
* This should be an uncommon occurrence, as they should always match. 
[Check Image Versions](https://console.demo.transposit.com/mc/t/spackle/actions/check_most_recent)
