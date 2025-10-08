# pgadmin-ubuntu
Tutorial de instalação e configuração de servidor no Ubuntu.

Testado no Ubuntu 22.04 e Mint 22.1, mas deve funcionar em outras distros baseadas em Debian.

## Instalação
#### Adicionando chave de repositório
~~~
curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add
~~~
#### Criando configuração de repositório
~~~
sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
~~~
#### Atualizar repositórios e instalar PgAdmin4
~~~
sudo apt update
~~~
~~~
sudo apt install pgadmin4
~~~
## Configuração
### Criar servidor e senha de usuário
**1- Acessar a shell de banco de dados**
~~~
sudo su - postgres
~~~
Então, Digite:
~~~
psql
~~~
Assim, você vai ver: 
```postgres=#```

**2- Criar usuário**
~~~
create user pgadmin with superuser password 'admin';
~~~
Se desejar, substitua o nome de usuário e a senha.

### Criando servidor no PgAdmin
1- Abra o PgAdmin.

2- Aperte com o botão direito em **Server**, selecione **Register > Server**

<img width="400" alt="image" src="https://github.com/user-attachments/assets/5809050d-826c-4465-80ef-03f0541ec280" />

3- Digite um nome para o servidor.

4- Na aba **Connections**, digite:
- Em Host name/adress: **localhost**
- Em username, o nome do usuário que criou. Neste caso, **pgadmin**
- Em password, a senha que criou. Neste caso, **admin**
<img width="600" alt="image" src="https://github.com/user-attachments/assets/5d49f4a1-ae7b-447e-9dc0-3b554bd0eedd" />

5- Clique em **Save**.

Pronto.
