# Git e Github - Setup (Conta Github)

Tag:: #Git/Setup #Setup
References: https://www.youtube.com/watch?v=alxRKszfTck&list=PLfCKf0-awunORbTiGbKnp7MlkXbT5lk1y&index=4 
https://docs.github.com/pt/github-ae@latest/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent #Github/Docs
## Configuração inicial

O procedimento abaixo será realizado em um Linux

### Configurando uma conta


Você deve mudar a penas o "Your NAME Comes Here" pode colocar o nome a seu gosto
```
git config --global user.name "Your NAME Comes Here"
```

Abaixo você deve mudar apenas o e-mail no qual a sua conta está cadastrada no github, no qual você faz o login:
Segue abaixo como cahar o mesmo:
![[../Attachments/email github.png]]
```
git config --global user.email e-mail@exemple.com
```


### Setup do Github

no seu terminal você deve gerar o comando abaixo para a criação da chave ssh para posteriormente acessar o github com ela:
```
ssh-keygen -t rsa -C "e-mail@exemple.com"
```

Para concluir o passo acima basta realizar os procedimentos abaixo:
	1 - Colocar o comando acima;  
	2 -  Inserir o nome da suas chaves ssh;
	3 - Escolher uma senha para as mesmas e repetir. 
	
	![[../Attachments/setu ssh.png]]

Gerando um agent para realizar o conectator do Github
```
eval "$(ssh-agent -s)"
```

Adicione sua chave SSH privada ao ssh-agent.
```
ssh-add ~/.ssh/chave_gerada
```

Agora temos que incluir a chave ssh gerada no github
	1 - Clicar em Settings;
	2 - Escolher a aba do lado esquerdo SSH and GPG Keys;
	3 - Escolha um nome para essa chave;
	4 - Abrir sua chave ssh gerada com no meu caso o nome do arquivo foi:  cat ~/.ssh/github_ti01.pub
	

![[../Attachments/ssh github.png]]

Testar conexão com o vinculo criado
**Obs:** já que eu não deixei o meu arquivo ssh com o nome padrão temos que colocar o parametro '-i' 
```
ssh -T -i ~/.ssh/chave_gerada git@github.com
```

