## OCI Testing 
----------


172.16.2.0/24

129.146.186.12

ssh -i ~/Downloads/ opc@129.146.186.12

ssh-key-2020-11-15.key.pub

ssh -i ~/Downloads/ssh-key-2020-11-15.key opc@129.146.186.12



oci resource-manager stack create --compartment-id ocid1.tenancy.oc1..aaaaaaaayjnidkaek5nrvwotuw5t43bxcjbza2fvlp3ijrzoj7a4lnt6x4qq --config-source stack.zip --display-name "Demo Stack" --terraform-version "0.12.x"



oci resource-manager job create-plan-job --stack-id "ocid1.ormstack.oc1.phx.aaaaaaaac427rvbs4onft45s3x5n5yrn5b4p6zu2tzwp4za5cvectoee4hvq"




oci resource-manager job create-apply-job --stack-id "ocid1.ormstack.oc1.phx.aaaaaaaac427rvbs4onft45s3x5n5yrn5b4p6zu2tzwp4za5cvectoee4hvq" --execution-plan-strategy "FROM_PLAN_JOB_ID" --execution-plan-job-id "ocid1.ormjob.oc1.phx.aaaaaaaauoqgcy5ewjydep6vgki4ylwohn7mmsbba2svbkeni5gkupm5z6la"



oci resource-manager stack update --config-source stack.zip --stack-id ocid1.ormstack.oc1.phx.aaaaaaaac427rvbs4onft45s3x5n5yrn5b4p6zu2tzwp4za5cvectoee4hvq

oci resource-manager  job create-apply-job --stack-id ocid1.ormstack.oc1.phx.aaaaaaaac427rvbs4onft45s3x5n5yrn5b4p6zu2tzwp4za5cvectoee4hvq --execution-plan-strategy "AUTO_APPROVED"


