# notes-app-api

A Serverless note application api

### Useful commands
Testing the create function  
`serverless invoke local --function create --path mocks/create-event.json`

Testing the get single note function  
`serverless invoke local --function get --path mocks/get-event.json`

Testing the list all notes function  
`serverless invoke local --function list --path mocks/list-event.json`

Testing the update note function  
`serverless invoke local --function update --path mocks/update-event.json`

Testing the delete note function  
`serverless invoke local --function delete --path mocks/delete-event.json`

Deploying the functions to aws  
`serverless deploy`

Deploying a single function  
`serverless deploy function list`

Testing the deployed api  

```bash
npx aws-api-gateway-cli-test \
--username='admin@example.com' \
--password='Passw0rd!' \
--user-pool-id='YOUR_COGNITO_USER_POOL_ID' \
--app-client-id='YOUR_COGNITO_APP_CLIENT_ID' \
--cognito-region='YOUR_COGNITO_REGION' \
--identity-pool-id='YOUR_IDENTITY_POOL_ID' \
--invoke-url='YOUR_API_GATEWAY_URL' \
--api-gateway-region='YOUR_API_GATEWAY_REGION' \
--path-template='/notes' \
--method='POST' \
--body='{"content":"hello world","attachment":"hello.jpg"}'

```
