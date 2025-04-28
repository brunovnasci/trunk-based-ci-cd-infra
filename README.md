# trunk-based-ci-cd-infra

Criar instancia SonarQube:
```bash
aws cloudformation create-stack --stack-name sonarqube --template-body file://infra/ec2.sonarqube.template.yaml
```

Eliminar instancia SonarQube:
```bash
aws cloudformation delete-stack --stack-name sonarqube
```

Criar repositorio ECR
```bash
aws cloudformation create-stack --stack-name banking-accounts-ecr-repository --template-body file://infra/ecr.repository.template.yaml
```

Atualizar repositorio ECR
```bash
aws cloudformation update-stack --stack-name banking-accounts-ecr-repository --template-body file://infra/ecr.repository.template.yaml
```

Eliminar repositorio ECR
```bash
aws cloudformation delete-stack --stack-name banking-accounts-ecr-repository
``` 

Criar cluster ECS:
```bash
aws cloudformation create-stack --stack-name tcc-ecs-cluster --template-body file://infra/ecs.cluster.template.yaml --capabilities CAPABILITY_NAMED_IAM
```

Eliminar cluster ECS:
```bash
aws cloudformation delete-stack --stack-name tcc-cluster
```

Criar serviço ECS dev
```bash
aws cloudformation create-stack --stack-name banking-accounts-ecs-service-dev --template-body file://infra/ecs.service.template.yaml --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=EnvironmentName,ParameterValue=dev
```

Atualizar serviço ECS dev
```bash
aws cloudformation update-stack --stack-name banking-accounts-ecs-service-dev --template-body file://infra/ecs.service.template.yaml --capabilities CAPABILITY_NAMED_IAM
```

Eliminar serviço ECS dev
```bash
aws cloudformation delete-stack --stack-name banking-accounts-ecs-service-dev
``` 

Criar serviço ECS prod
```bash
aws cloudformation create-stack --stack-name banking-accounts-ecs-service-prod --template-body file://infra/ecs.service.template.yaml --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=EnvironmentName,ParameterValue=prod
```

Atualizar serviço ECS prod
```bash
aws cloudformation update-stack --stack-name banking-accounts-ecs-service-prod --template-body file://infra/ecs.service.template.yaml --capabilities CAPABILITY_NAMED_IAM
```

Eliminar serviço ECS prod
```bash
aws cloudformation delete-stack --stack-name banking-accounts-ecs-service-prod
``` 

Criar OIDC para o Github Actions
```bash
aws cloudformation create-stack --stack-name banking-accounts-oidc-github-actions --template-body file://infra/iam.oidc.template.yaml --capabilities CAPABILITY_NAMED_IAM
```

Eliminar OIDC
```bash
aws cloudformation delete-stack --stack-name banking-accounts-oidc-github-actions
```
