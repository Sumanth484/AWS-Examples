## Create cluster by updating template.yaml

```sh
sh ./deploy
```
## Create Log Group

aws logs create-log-group --log-group-name ecs-fargate

## Create our Task Def

aws ecs register-task-definition --cli-input-json file://task-def.json

## Deploy Container

aws ecs create-service --cli-input-json file://serv.json

# ECS Exec

## Installing SM CLI for AWS CLI on Ubunutu

https://docs.aws.amazon.com/systems-manager/latest/userguide/install-plugin-debian-and-ubuntu.html

```sh
curl "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/ubuntu_64bit/session-manager-plugin.deb" -o "session-manager-plugin.deb"
sudo dpkg -i session-manager-plugin.deb
```

## Connect to Container Env

```sh
aws ecs execute-command \
--cluster ecs-fargate-basicECSCluster \
--task 050667c509af4b52adaf67a5f2b66f08 \
--container app \
--interactive \
--command "/bin/sh"
```

