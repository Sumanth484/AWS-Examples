## Create Trust policy and mention assume services

## Create role by attaching trust policy

```sh
aws iam create-role \
--role-name Test-Role \
--assume-role-policy-document file://trust-policy.json
```

## Create a policy and attatch it to role

```sh
aws iam put-role-policy \
--role-name Test-Role \
--policy-name TestPolicy \
--policy-document file://task.json
```