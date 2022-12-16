# Multiple SSH keys for work or personal project 


## Múltiplas chave SSH para projeto de trabalho ou pessoal

- Criar pasta de trabalho
- Criar chave ssh par trabalho
- Configurar a nova chave ssh no Github
- Configurar um arquivo com parâmetros que vão sobre escrver o .gitconfig padrão
- Informar no .gitconfig padrão qual o nome da pasta dos projetos profissionais e o nome do arquivo de configurações
- Criar dentro da pasta .ssh um arquivo de configuração par os alias do ssh. "config"

### Organizando git e suas chaves ssh para trabalhos profissionais

### Arquivo de configuração padrão do seu usuário ".gitconfig"
```
[user]
  name = "seu nome"
  email = "seu email pessoal"

[init]
  defaultBranch = main

[includeIf "gitdir:<caminho para a pasta de trabalho>"]
  path = <caminho e nome do arquivo de configuração do git de trabalho>
```

---

### Arquivo localizado na sua pasta de trabalhos ".gitconfig-work"

```
[user]
  name = "Nome do seu usuário de trabalho"
  email = "email de trabalho"

[core]
  sshCommand = ssh -i ~/.ssh/<nome da sua chave ssh pra trabalho>
```

### Arquivo config na masta .ssh
```
# Conta pessoal
Host github.com
   HostName github.com
   User git
   IdentityFile ~/.ssh/<nome da chave ssh para a conta pessoal>
   
# Conta de trabalho
Host github.com-work  
   HostName github.com
   User git
   IdentityFile ~/.ssh/<nome da chave ssh para a conta de trabalho>

```


