# josh runbook

## ECR / Elastic Container Registry

All our images for all environments are stored on the development-admin ECR account. 
ECS pulls the most recent images from ECR to spin up new tasks.

## Verify ECS Images
[Check that the most recent image is deployed](https://console.demo.transposit.com/mc/t/spackle/actions/check_most_recent) in ECS.
This should be an uncommon occurrence, as they should always match. 
If they don’t match, Click here to do something
