<h1>MySQL dentro do docker </h1>
<p>Copiar o dump para o ambiente docker do MySQL.</p>

<h2>1º verifique e copie o ID do contêiner para o docker do MySQL:</h2>

| sudo docker ps

<p>Copie o arquivo de despejo SQL em seu contêiner usando:</p>

| sudo docker cp /path_caminho/file.sql MysqlDockerID:/

<p>Isso copiará o arquivo de despejo para a pasta raiz do docker</p>

<h2>2º Agora, para interagir com o MySQL dentro de um contêiner em execução, execute o seguinte comando: </h2>

| sudo docker exec -it MysqlDockerID bin/bash

<h2>3º Agora conecte-se ao MySQL usando o terminal: </h2>

| mysql -u yourUserName -p

<h2>Obs: solicitará a senha. Digite a senha correta para continuar. </h2>

<p>Liste os bancos de dados disponíveis por:</p>

| show Databases;

<p>Supondo que o nome do banco de dados para o qual deseja importar o dump seja 'MyDatabase'. Mude para isso usando:</p>

| use MyDatabase

<h2>4º Importar o arquivo digitando: </h2>

| source file.sql

<h2>Obs: Lembre-se de que o comando acima funciona se você copiou o arquivo para a pasta raiz (usando a etapa 2). </h2>
