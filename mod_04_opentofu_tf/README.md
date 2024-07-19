# Infraestructura mediante usando Open Tofu

Requerido tener variable de entorno:
```shell
export DIGITALOCEAN_ACCESS_TOKEN=dop_v1_XXXXXXXXXXXXXXXXXXXXXXXX
```

Ejemplo de crear VM
```
resource "digitalocean_droplet" "iac-everyone-server-1" {
  image      = "debian-12-x64"
  name       = "iac-everyone-server-1"
  region     = "nyc1"
  size       = "s-1vcpu-512mb-10gb"
  vpc_uuid   = digitalocean_vpc.iac-vpc.id
  ssh_keys   = [
    data.digitalocean_ssh_key.iac_for_everyone_ssh_key.id
  ]
}
```
