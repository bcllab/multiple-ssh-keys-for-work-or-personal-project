# Multiple SSH keys for work or personal project 


## Múltiplas chave SSH para projeto de trabalho ou pessoal

- Criar pasta de trabalho
- Criar chave ssh par trabalho
- Configurar a nova chave ssh no Github
- Configurar um arquivo com parâmetros que vão sobre escrver o .gitconfig padrão
- Informar no .gitconfig padrão qual o nome da pasta dos projetos profissionais e o nome do arquivo de configurações

### Organizando git e suas chaves ssh para trabalhos profissionais

- Arquivo localizado na pasta HOME do seu usuário

ex.: ~/.gitconfig

### .gitconfig
```
[user]
  email = "seu email pessoal"
  name = "seu nome"

[init]
  defaultBranch = main

[includeIf "gitdir:<caminho para a pasta de trabalho>"]
  path = <caminho e nome da sua chave ssh>
```

---

Arquivo localizado na sua pasta de trabalhos profissionais

Ex.: ~/BCL-LAB/.gitconfigForBCL-LAB

### .gitconfigForBCL-LAB

```
[user]
  name = "Nome do seu usuário"
  email = "email de trabalho"

[core]
  sshCommand = ssh -i ~/.ssh/<nome da sua chave ssh>
```

###
