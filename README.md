
O que é o Docker?

O Docker é uma aplicação que torna simples e fácil executar processos de aplicação em um contêiner, 
que é como uma máquina virtual, apenas mais portátil, mais amigável, e mais dependente do sistema 
operacional do host.

>Nota: O Docker requer uma versão de 64 bits, bem como uma versão de kernel maior ou igual 
a 3.10.




Instação do Docker

Executar um scritp de instalação, adicionar um repositório na máquina e já fazendo a instalação.

	#curl -sSL https://get.docker.com | sh

Iniciar o docker

	#/etc/init.d/docker start

Verificar se o docker está rodando

	#ps -ef | grep docker

	#docker ps

Criar um container do Ubuntu 16.04
(a porta 8080 é da maquina fisoca (host), a porta 80 é a do container,
/bin/bash é o processo da imagem será iniciada)

	#docker run -i -t -p 8080:80 ubuntu:16.04 /bin/bash
	

Quando termina de fazer o download ele já cria e entra no container

	#uname -a
	#cat /etc/issue

Atualizar o banco de dados de pacotes

	#apt-get update

Instalar o apache

	#apt-get install apache2

Inicie o apache

	#/etc/init.d/apache2 start

Ao terminar a instalação, abra o navegador com seu IP:

Para salvar as alterações feitas no container, vamos fazer um commit:

	#docker commit "ID do container" "nome pra imagem/apache2-ubuntu:1.0"

Para subir o container:

	#docker run -ti -p 8080:80 "nome pra imagem/apache2-ubuntu:1.0" /bin/bash


_______________________________________________________
Alguns comandos:

Sair sem encerrar o container:

	ctrl+p+q

Sair e encerrar a máquina:

	ctrl+d

Lista o status dos containers

	#docker ps -a

Lista as imagens baixada

	#docker images

Verificar as alterações do container
(Mostra todos os arquivos criados e deletados ou modificados)

	#docker diff "ID do container"

Voltar (ou entar) para o container

	#docker attach "ID do container"
