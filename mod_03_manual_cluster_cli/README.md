# Infraestructura mediante Digital Ocean CLI

1. Configurar DO Token
```shell
export DIGITALOCEAN_ACCESS_TOKEN=dop_v1_XXXXXXXXXXXXXXXXXXXXXXXX
```
1. Crear VPC
```
doctl vpcs create --name iac-vpc --region nyc1
```

2. Listar VPCs
```shell
doctl vpcs list
```

2. Crear MV (Droplet) en el VPC creado
```shell
doctl compute droplet create \
    --image debian-12-x64 \
    --size s-1vcpu-512mb-10gb \
    --region nyc1 \
    --enable-monitoring \
    --vpc-uuid XXXXXXXX-5548-4890-bb1a-aee33b24c4cb \
    iac-everyone-server-1
```

3. Listar VMs. Tambien podemos ir por la consola web.
```shell
doctl compute droplet list 
```

5. Borrar recursos
```shell
doctl compute droplet delete iac-everyone-server-1
doctl vpcs delete XXXXXXXX-5548-4890-bb1a-aee33b24c4cb
```