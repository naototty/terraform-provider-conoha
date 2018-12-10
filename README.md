# terraform-provider-conoha
Terraform plugin for ConoHa -- this project is still a work in progress.

supported API
* DNS v1

ConoHa DNS API is OpenStack Designate DNS v1 and v2 at Kilo release API.
However, the current OpenStack DNS API is v2 only support.
terraform-provider-openstack also supports only DNS v2.

## Install
Just `go get && go build` and copy `terraform-provider-conoha` into the same directory as your `terraform` executable.

## Example

```hcl
provider "conoha" {
  region = "tyo1"
}

resource "conoha_compute_keypair" "anzu" {
  name = "anzu"
  public_key = "ssh-rsa XXXXXXXXXXXXXXX anzu@localhost"
}

resource "conoha_dns_domain" "example_com" {
  name = "exmaple.com."
  email = "webmaster@example.com"
}

```
