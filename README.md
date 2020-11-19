<!-- This file was automatically generated by the `geine`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->

<p align="center"> <img src="https://user-images.githubusercontent.com/50652676/62349836-882fef80-b51e-11e9-99e3-7b974309c7e3.png" width="100" height="100"></p>


<h1 align="center">
    Terraform AWS Lightsail
</h1>

<p align="center" style="font-size: 1.2rem;"> 
    Terraform module to create Lightsail instance, Lightsail Key Pair
(Optional), Lightsail Static IP (Optional).
     </p>

<p align="center">

<a href="https://www.terraform.io">
  <img src="https://img.shields.io/badge/Terraform-v0.13-green" alt="Terraform">
</a>
<a href="LICENSE.md">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="Licence">
</a>


</p>
<p align="center">

<a href='https://facebook.com/sharer/sharer.php?u=https://github.com/clouddrove/terraform-aws-lightsail'>
  <img title="Share on Facebook" src="https://user-images.githubusercontent.com/50652676/62817743-4f64cb80-bb59-11e9-90c7-b057252ded50.png" />
</a>
<a href='https://www.linkedin.com/shareArticle?mini=true&title=Terraform+AWS+Lightsail&url=https://github.com/clouddrove/terraform-aws-lightsail'>
  <img title="Share on LinkedIn" src="https://user-images.githubusercontent.com/50652676/62817742-4e339e80-bb59-11e9-87b9-a1f68cae1049.png" />
</a>
<a href='https://twitter.com/intent/tweet/?text=Terraform+AWS+Lightsail&url=https://github.com/clouddrove/terraform-aws-lightsail'>
  <img title="Share on Twitter" src="https://user-images.githubusercontent.com/50652676/62817740-4c69db00-bb59-11e9-8a79-3580fbbf6d5c.png" />
</a>

</p>
<hr>


We eat, drink, sleep and most importantly love **DevOps**. We are working towards strategies for standardizing architecture while ensuring security for the infrastructure. We are strong believer of the philosophy <b>Bigger problems are always solved by breaking them into smaller manageable problems</b>. Resonating with microservices architecture, it is considered best-practice to run database, cluster, storage in smaller <b>connected yet manageable pieces</b> within the infrastructure. 

This module is basically combination of [Terraform open source](https://www.terraform.io/) and includes automatation tests and examples. It also helps to create and improve your infrastructure with minimalistic code instead of maintaining the whole infrastructure code yourself.

We have [*fifty plus terraform modules*][terraform_modules]. A few of them are comepleted and are available for open source usage while a few others are in progress.




## Prerequisites

This module has a few dependencies: 

- [Terraform 0.13](https://learn.hashicorp.com/terraform/getting-started/install.html)
- [Go](https://golang.org/doc/install)
- [github.com/stretchr/testify/assert](https://github.com/stretchr/testify)
- [github.com/gruntwork-io/terratest/modules/terraform](https://github.com/gruntwork-io/terratest)







## Examples


**IMPORTANT:** Since the `master` branch used in `source` varies based on new modifications, we suggest that you use the release versions [here](https://github.com/clouddrove/terraform-aws-lightsail/releases).


### Simple Example
Here is an example of how you can use this module in your inventory structure:
```hcl
# Github =
    module "lightsail" {
      source        = "git::https://github.com/clouddrove/terraform-lightsail.git?ref=tags/0.13.0"
      environment   = "prod"
      name          = "lightsail"
      key_pair_name = "testing"
      application   = "clouddrove"
      label_order   = ["environment", "application", "name"]
   }
```






## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| application | Application (e.g. `cd` or `clouddrove`). | `string` | `""` | no |
| attributes | Additional attributes (e.g. `1`). | `list` | `[]` | no |
| availability\_zone | The Availability Zone in which to create your instance | `string` | `"ap-south-1a"` | no |
| blueprint\_id | The ID for a virtual private server image | `string` | `"ubuntu_16_04_2"` | no |
| bundle\_id | The bundle of specification information | `string` | `"micro_2_1"` | no |
| create\_static\_ip | Create and attach a statis IP to the instance | `bool` | `false` | no |
| delimiter | Delimiter to be used between `organization`, `environment`, `name` and `attributes`. | `string` | `"-"` | no |
| environment | Environment, e.g. 'prod', 'staging', 'dev', 'pre-prod', 'UAT' | `string` | n/a | yes |
| instance\_count | Number of instances to launch. | `number` | `1` | no |
| instance\_enabled | Flag to control the instance creation. | `bool` | `true` | no |
| key\_pair\_name | The key name to use for the instance. | `string` | `""` | no |
| label\_order | Label order, e.g. `name`,`application`. | `list` | `[]` | no |
| lightsail\_enabled | Flag to control the lightsail instance creation. | `bool` | `true` | no |
| managedby | ManagedBy, eg 'CloudDrove' or 'AnmolNagpal'. | `string` | `"anmol@clouddrove.com"` | no |
| name | Name  (e.g. `app` or `cluster`). | `string` | `""` | no |
| tags | Additional tags (e.g. map(`BusinessUnit`,`XYZ`). | `map` | `{}` | no |
| use\_default\_key\_pair | Default key pair name will be used, you must keep 'key\_pair\_name' empty | `string` | `"true"` | no |
| user\_data | launch script to configure server with additional user data | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| arn | Module      : Lightsail Description : Terraform module to create Lightsail instance, Lightsail Key Pair (Optional), Lightsail Static IP (Optional) resource on AWS. |
| availability\_zone | n/a |
| blueprint\_id | n/a |
| bundle\_id | n/a |
| created\_at | n/a |
| id | n/a |
| ip\_address | n/a |
| key\_pair\_name | n/a |
| staticip\_arn | n/a |
| tags | A mapping of tags to assign to the resource. |
| user\_data | n/a |




## Testing
In this module testing is performed with [terratest](https://github.com/gruntwork-io/terratest) and it creates a small piece of infrastructure, matches the output like ARN, ID and Tags name etc and destroy infrastructure in your AWS account. This testing is written in GO, so you need a [GO environment](https://golang.org/doc/install) in your system. 

You need to run the following command in the testing folder:
```hcl
  go test -run Test
```



## Feedback 
If you come accross a bug or have any feedback, please log it in our [issue tracker](https://github.com/clouddrove/terraform-aws-lightsail/issues), or feel free to drop us an email at [hello@clouddrove.com](mailto:hello@clouddrove.com).

If you have found it worth your time, go ahead and give us a ★ on [our GitHub](https://github.com/clouddrove/terraform-aws-lightsail)!

## About us

At [CloudDrove][website], we offer expert guidance, implementation support and services to help organisations accelerate their journey to the cloud. Our services include docker and container orchestration, cloud migration and adoption, infrastructure automation, application modernisation and remediation, and performance engineering.

<p align="center">We are <b> The Cloud Experts!</b></p>
<hr />
<p align="center">We ❤️  <a href="https://github.com/clouddrove">Open Source</a> and you can check out <a href="https://github.com/clouddrove">our other modules</a> to get help with your new Cloud ideas.</p>

  [website]: https://clouddrove.com
  [github]: https://github.com/clouddrove
  [linkedin]: https://cpco.io/linkedin
  [twitter]: https://twitter.com/clouddrove/
  [email]: https://clouddrove.com/contact-us.html
  [terraform_modules]: https://github.com/clouddrove?utf8=%E2%9C%93&q=terraform-&type=&language=
