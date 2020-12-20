# CloudformationProject
This project is to deploy an application along with the necessary software into its matching infrastructure in an *AWS console*.

## The files _create.sh and update.sh_ are used to create the infrastructure and update infrasturcture with the changes made.

Content of the create.sh file
```
#!/bin/bash
aws cloudformation create-stack \
--stack-name $1 \
--template-body file://$2 \
--parameters file://$3 \
--region=us-west-2

```
