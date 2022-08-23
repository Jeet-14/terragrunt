# terragrunt

This repo conatatins sample terragrunt code whcih will deploy similar infra on multiple account/regions/envs.

- Currently the tree structure is as follows:

There is terragrunt.hcl file at root location which includes remote backend configuration and provider configuration including profile to be use. 

All the s3 modules in each env will inherit these config from parent dir. Each modules have it's own state file in s3.


 ```
 .
├── dev
│   └── s3
│       └── terragrunt.hcl
├── prod
│   └── s3
│       └── terragrunt.hcl
├── qa
│   └── s3
│       └── terragrunt.hcl
└── terragrunt.hcl
 ``` 

 To execute terraform command on multiple module at once, run following from root folder
 ```
 terragrunt run-all apply
 ```