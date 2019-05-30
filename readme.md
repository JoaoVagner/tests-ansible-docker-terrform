# Terraform

Para planejar a aplicação do terraform na AWS siga os seguintes procedimentos:

### auto.tfvars

Abra o arquivo auto.tfvars e altere as chaves da AWS assim como o caminho dos arquivos da chave

Para executar o planejamento:

```
terraform plan -var-file auto.tfvars 
```

Para executar a aplicação execute:

```
terraform apply -var-file auto.tfvars 
```

Para destruir toda a construção, execute:

```
terraform destroy -var-file auto.tfvars 
```



# Ansible
Antes de começar, inicie adicionando a chave chave no console da AWS com o nome aws.pem e adicione ao seu agent usando ssh-add:

```bash
ssh-add ~/.ssh/aws.pem
```

Agora altere o arquivo ssh_config e o hosts colocando os IPS adequados nas seguintes entradas:

__hosts__:

**IP-manager-$** - Troque esses valores pelos IPS dos managers

**IP-WORKER-$** - Troque esses valores pelos IPS dos workers


Agora altere o arquivo ssh_config e no Host nat.ec2 troque o Hostname IP da NAT para poder configurar seu salto SSH e conectar na rede privada através da NAT.

Agora na pasta *test-ansible/* execute:

```
ansible-playbook -i hosts  main.yml
```














