**Projeto de Conhecimento Inicial com Docker**  

Este projeto tem como objetivo demonstrar os conhecimentos iniciais adquiridos em Docker durante o curso na Trybe. Nele, foram realizadas uma série de tarefas relacionadas à criação de containers, gerenciamento de imagens e execução de serviços.

**Tarefas Realizadas**

1. Criação do Container "01container"  
**Descrição**: Criei um container em modo interativo, sem rodá-lo, nomeando-o como 01container e utilizando a imagem alpine na versão 3.12.
Comando:
```bash
docker create -it --name 01container alpine:3.12
```
Resultado: O container foi criado com sucesso e está pronto para uso.  

2. Inicialização do Container "01container"
**Descrição**: Iniciei o container 01container que foi previamente criado.  
Comando:
```bash
docker start 01container
```
Resultado: O container 01container foi iniciado com sucesso.  

3. Listagem dos Containers pelo Nome "01container"
**Descrição**: Liste os containers filtrando pelo nome 01container.  
Comando:
```bash
docker ps -a --filter "name=01container"
```
Resultado: A lista de containers foi exibida, mostrando informações apenas do 01container.  

4. Execução do Comando cat /etc/os-release no Container "01container"
**Descrição**: Executei o comando cat /etc/os-release no container 01container sem me acoplar a ele.  
Comando:
```bash
docker exec 01container cat /etc/os-release
```
Resultado: Os dados da distribuição no container foram exibidos corretamente.  

5. Remoção do Container "01container"
**Descrição**: Removi o container 01container que havia sido criado anteriormente.  
Comando:
```bash
docker rm 01container
```
Resultado: O container 01container foi removido com sucesso.  

6. Download da Imagem nginx com a Versão 1.21.3-alpine
**Descrição**: Baixei a imagem nginx com a versão 1.21.3-alpine sem criar ou rodar um container.  
Comando:
```bash
docker pull nginx:1.21.3-alpine
```
Resultado: A imagem nginx na versão especificada foi baixada sem iniciar nenhum container.  

7. Criação de um Novo Container com a Imagem nginx na Versão 1.21.3-alpine
**Descrição**: Criei um novo container com a imagem nginx na versão 1.21.3-alpine, rodando em segundo plano e nomeando-o como 02images. Mapeei sua porta padrão de acesso para a porta 3000 do sistema hospedeiro.  
Comando:
```bash
docker run -d --name 02images -p 3000:80 nginx:1.21.3-alpine
```
Resultado: O container 02images foi criado e está executando o serviço do Nginx na porta 3000 do sistema hospedeiro.  

8. Parada do Container "02images"
**Descrição**: Parei o container 02images que estava em execução.  
Comando:
```bash
docker stop 02images
```
Resultado: O container 02images foi interrompido e não está mais em execução. 

9. Criação da Imagem todobackend a partir do Dockerfile do "back-end" do "todo-app"
**Descrição**: Criei uma imagem chamada todobackend a partir do Dockerfile do "back-end" do "todo-app". A imagem foi configurada para rodar a partir da imagem node:14-alpine, expondo a porta 3001 e incluindo o arquivo node_modules.tar.gz e todos os arquivos da pasta back-end. A aplicação é iniciada com o comando npm start.  
Comando:
```bash
docker build -t todobackend ./docker/todo-app/back-end
```
Resultado: A imagem todobackend foi criada com sucesso a partir do Dockerfile especificado.  

10. Criação da Imagem todofrontend a partir do Dockerfile do "front-end" do "todo-app"
**Descrição**: Criei uma imagem chamada todofrontend a partir do Dockerfile do "front-end" do "todo-app". A imagem foi configurada para rodar a partir da imagem node:14-alpine, expondo a porta 3000 e incluindo o arquivo node_modules.tar.gz e todos os arquivos da pasta front-end. A aplicação é iniciada com o comando npm start.  
Comando:
```bash
docker build -t todofrontend ./docker/todo-app/front-end
```
Resultado: A imagem todofrontend foi criada com sucesso a partir do Dockerfile especificado.  

11. Criação da Imagem todotests a partir do Dockerfile dos Testes do "todo-app"
**Descrição**: Criei uma imagem chamada todotests a partir do Dockerfile dos testes do "todo-app". A imagem foi configurada para rodar a partir da imagem mjgargani/puppeteer:trybe1.0 e incluir o arquivo node_modules.tar.gz e todos os arquivos da pasta tests. Os testes são iniciados com o comando npm test.  
Comando:
```bash
docker build -t todotests ./docker/todo-app/tests
```
Resultado: A imagem todotests foi criada com sucesso a partir do Dockerfile especificado.  

**Como Executar**
Clone o repositório em sua máquina local.
Execute o Docker Compose para iniciar a orquestração de serviços:
```bash
docker-compose up -d
```
**Considerações Finais**
Este projeto me proporcionou a oportunidade de aprender e aplicar conceitos importantes relacionados ao Docker. Fique à vontade para explorar os serviços e as imagens criadas neste projeto.
