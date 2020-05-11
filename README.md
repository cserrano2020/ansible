# Ansible

# Projeto Apache
Esse projeto contempla a utilização do Ansible, Docker, Docker Hub e Git para provisionar uma container Alpine com Apache com a página index.html elaborada pelo time de desenvolvimento.

# Requirementos
Ansible 2.9.7
Docker version 19.03.8
Conta no Git e Docker Hub

# Utilização

1 - Realize o clone desse repositório;

2 - Acesse o diretório ./group_vars e configure o usuário e senha no arquivo servidores do seu ambiente;

3 - Acesse o arquivo hosts e ajuste o servidor de destino no grupo [servidores], no caso, estamos utilizando o servidor local (127.0.0.1);

4 - Acesse o diretório ./playbook e execute o comando abaixo;
ansible-playbook create-simple-devops-image-apache.yml

Nesse passo iremos parametrizar as pastas no servidor de destino, clonar o repositório com a pagina index.html elaborada pelo time de desenvolvimento, copiar o Dockerfile, criar uma imagem Alpine com Apache , criar as tags na imagem e empurrar para o Docker Hub e apagar localmente. 

5 - Acesse o diretório ./playbook e execute o comando abaixo;
ansible-playbook create-simple-devops-project-apache.yml

Nesse passo iremos remover um container existente, remover a imagem local, baixar a imagem do Docker Hub e criar o container montanto o volume que contém a página index.html.

6 - Acessa a página localmente com http://localhost ou remotamente com http://ip_do_servidor/index.html

Com esses dois playbooks, podemos utilizar o Jenkis em nosso pipeline, após o commit do desenvolvedor no repositório da página, o Job do Jenkins poderá rodar os playbooks novamente mantendo sempre o container atualizado.

# Autor
Carlos Henrique Serrano
www.linkedin.com/in/carloshenriqueserrano
