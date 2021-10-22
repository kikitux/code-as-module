# code-as-module
this is a repo with code that can be used as module

## About this repo

This is code that can be used as modudle

# how to use

## Create terraform code that uses this code as module

```
module mymodule {
  source = "github.com/kikitux/code-as-module"
}
```

## terraform init

## terraform plan

## terraform apply

# Sample output

```

test % terraform init
Initializing modules...
Downloading github.com/kikitux/code-as-module for mymodule...
- mymodule in .terraform/modules/mymodule

Initializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/null...
- Installing hashicorp/null v3.1.0...
- Installed hashicorp/null v3.1.0 (signed by HashiCorp)

Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
test % terraform plan

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # module.mymodule.null_resource.mynull will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.

──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.
test % terraform apply

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # module.mymodule.null_resource.mynull will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

module.mymodule.null_resource.mynull: Creating...
module.mymodule.null_resource.mynull: Creation complete after 0s [id=807439471107685958]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
test % 

```
