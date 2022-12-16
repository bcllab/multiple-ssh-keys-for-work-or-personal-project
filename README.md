# Multiple SSH keys for work or personal project 


## Múltiplas chave SSH para projeto pessoal ou profissional

- Criar pasta de trabalho
- Criar chave ssh par trabalho
- Configurar a nova chave ssh no Github
- Configurar um arquivo com parâmetros que vão sobre escrver o .gitconfig padrão
- Informar no .gitconfig padrão qual o nome da pasta dos projetos profissionais e o nome do arquivo de configurações
- Criar dentro da pasta .ssh um arquivo de configuração par os alias do ssh. "config"
- Reiniciar o computador
- Testar conexãoe chaves como servidor do github


## Organizando o Git e as chaves SSH

### Arquivo de configuração padrão do seu usuário ".gitconfig"

.gitconfig
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

### Arquivo localizado na sua pasta de trabalho ".gitconfig-work"

.gitconfig-work
```
[user]
  name = "Nome do seu usuário de trabalho"
  email = "email de trabalho"

[core]
  sshCommand = ssh -i ~/.ssh/<nome da sua chave ssh pra trabalho>
```

### Arquivo "config" localizado na pasta ~/.ssh/

config
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

### Testando conexão e chaves ssh como o servidor do GitHub

Exemplo:

```
cd ~/work

ssh git@github.com

ssh git@github.com-work
```


