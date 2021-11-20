Used to automate and manage infrastructure, platform and services that run on platform. It is used to provision infrastructure and deploy applications.

Provisioing infrastructure could mean installing Private network space, EC2 server instance, install docker and other tools, install security (firewalls) and network.

Terraform is different to Ansible in a way that Terraform is infrastructure provisioning tool where as Ansible is a configuration tool to configure infrastructure, deploy apps, install/ update software.

We can replicate infrastructure using terraform - dev, stage, prod

# How Terraform Works

Terraform has 2 main components: Core and Provider

Core has TF Config where we define what needs to be created and provisioned. Core has TF state where terraform updates itself how the current setup of infrastructure looks like. Core looks at plan and decides what needs to be created / updated / destroyed in what order.

Providers are there for specific technologies like AWS/ Azure and higher level components like Kubernetes, software as services like Fastly etc. Terraform has more than 100 providers. Through the AWS provider, we have access to 100 AWS resources.

Once the core creates the execution plan using config, it uses providers to execute the plan.

## Declarative Language
Define WHAT end result you want. In the declarative state, we define the end state of our config file. We adjust the old config file and re-execute it.

## Imperative Language
Define exact steps - HOW. In the imperative state while updating infrastructure, we give instructions.

If we use lambda resources inside terraform, terraform becomes imperative restricted by declarative HCL.

## Terraform Commands
Once desired state is defined, terraform executes the following commands (usually defined in CI) :

Refresh - query infrastructure provider to get current state
Plan - create execution plan
Apply - Execute the plan
Destroy - Destroy resources/ infrastructure in defined order



