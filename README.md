
-- Get pods in the current default namespace

``` 
kubectl get po 
```

-- Run Infra manifests from `manifests` folder

``` 
kubectl create -f infra/
```

-- Run App manifest from `manifests` folder

```
kubectl create -f app/account-service
kubectl create -f app/notfiication-service
```


`curl` command to create an account

```
curl -v --location --request POST 'http://172.18.0.3:30844/api/accounts' \
--header 'Content-Type: application/json' \
--data-raw '{
"customerId": "CUST9999",
"accountType": "SAVINGS"
}'
```

`curl` command to create a transaction

```
curl -v --location --request POST 'http://172.18.0.3:30844/api/transactions' \
--header 'Content-Type: application/json' \
--data-raw '{
"accountId": "ACC2832545",
"amount": 100,
"description": "Token Amount",
"transactionType": "DEPOSIT"
}'
```

Command to get the node where the container is deployed

```
kubectl get pods -o wide
```

Command to get the node ip address

```
kubelct get nodes -o wide
```