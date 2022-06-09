## Meu Cloud com LocalStack

Simulação de um ambiente AWS Cloud em minha máquina local usando o LocalStack.

```bash
┏━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Runtime version ┃ 0.14.4.dev                                            ┃
│ Docker image    │ tag: latest, id: 625ca7523df2, 📆 2022-06-08T16:49:50 │
│ Runtime status  │ ✔ running (name: "localstack_main", IP: 172.17.0.2)   │
└─────────────────┴───────────────────────────────────────────────────────┘
┏━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━┓
┃ Service                  ┃ Status      ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━┩
│ acm                      │ ✔ running   │
│ apigateway               │ ✔ available │
│ cloudformation           │ ✔ available │
│ cloudwatch               │ ✔ available │
│ config                   │ ✔ available │
│ dynamodb                 │ ✔ available │
│ dynamodbstreams          │ ✔ available │
│ ec2                      │ ✔ running   │
│ es                       │ ✔ available │
│ events                   │ ✔ available │
│ firehose                 │ ✔ available │
│ iam                      │ ✔ running   │
│ kinesis                  │ ✔ available │
│ kms                      │ ✔ available │
│ lambda                   │ ✔ available │
│ logs                     │ ✔ available │
│ opensearch               │ ✔ available │
│ redshift                 │ ✔ available │
│ resource-groups          │ ✔ available │
│ resourcegroupstaggingapi │ ✔ available │
│ route53                  │ ✔ running   │
│ route53resolver          │ ✔ available │
│ s3                       │ ✔ running   │
│ s3control                │ ✔ available │
│ secretsmanager           │ ✔ available │
│ ses                      │ ✔ available │
│ sns                      │ ✔ available │
│ sqs                      │ ✔ available │
│ ssm                      │ ✔ available │
│ stepfunctions            │ ✔ available │
│ sts                      │ ✔ available │
│ support                  │ ✔ available │
│ swf                      │ ✔ available │
└──────────────────────────┴─────────────┘
```

---
### Requesitos

- docker
- python 3.9+
- pip3
- tfswitch ou terraform

---
### Instalação

```bash
pip3 install localstack

pip3 install awscli-local

pip3 install terraform-local
```

---
### Configuração inicial

```bash
export AWS_ACCESS_KEY_ID="test"
export AWS_SECRET_ACCESS_KEY="test"
export AWS_DEFAULT_REGION="us-east-1"
```

OBS.: Essa configuração inicial não precisa se vocẽ estiver usando os comando *awslocal* e *tflocal*!

---
### Iniciar e checar o localstack

```bash
localstack start -d
localstack status docker
localstack status services
```

---
### Comandos

- **AWS Cli:**
```bash
awslocal s3 ls
```

- **Teraform:**
```bash
tflocal init
tflocal plan
tflocal apply
tflocal destroy
```