# Elaboração de aplicação web integrada a um banco de dados

## Descrição do Projeto

Este projeto foi desenvolvido como parte de uma atividade acadêmica para demonstrar a integração de uma aplicação web com um banco de dados na AWS. O objetivo principal foi criar uma aplicação web que gerencie informações de jogadores de futebol e utilize recursos da AWS para hospedar e armazenar os dados.

[Assista ao vídeo no YouTube](https://youtu.be/oNPx3NkjiQM)

## Estrutura do Projeto

### Recursos Utilizados

1. **Amazon EC2 (Elastic Compute Cloud)**

   O servidor da aplicação web foi configurado utilizando uma instância EC2 da Amazon. A EC2 oferece a flexibilidade de configurar e gerenciar servidores virtuais na nuvem, permitindo a instalação e execução da aplicação web desenvolvida em PHP.

2. **Amazon RDS (Relational Database Service)**

   O banco de dados foi hospedado utilizando o Amazon RDS, um serviço gerenciado que facilita a configuração, operação e escalabilidade de bancos de dados relacionais na nuvem. Para esta atividade, foram criadas duas tabelas principais no banco de dados:

   - **Tabela Tutorial (Tutorial Table)**

     Esta tabela foi criada seguindo o [tutorial oficial da AWS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/TUT_WebAppWithRDS.html) e inclui os seguintes campos:
     
     - `ID` (inteiro, chave primária, auto-incremento)
     - `NAME` (VARCHAR)
     - `ADDRESS` (VARCHAR)

   - **Tabela Jogadores de Futebol (Football Players Table)**

     Esta tabela foi criada para gerenciar informações sobre jogadores de futebol e contém os seguintes campos:
     
     - `ID` (inteiro, chave primária, auto-incremento)
     - `NAME` (VARCHAR) - Nome do jogador
     - `POSITION` (VARCHAR) - Posição em campo
     - `TEAM` (VARCHAR) - Time atual do jogador
     - `AGE` (INT) - Idade do jogador

### Estrutura do Projeto

A aplicação web consiste em arquivos PHP que permitem a interação com o banco de dados e a manipulação de dados. Os arquivos principais são:

- **`jogadores_futebol.php`**: Página principal da aplicação que permite a visualização, criação, atualização e exclusão de registros de jogadores de futebol.
  <img src="https://raw.githubusercontent.com/pelinsarix/pelinsari_aws_ponderada/main/assets/jogadores.png"/>
- **`SamplePage.php`**: Página de amostra usada para demonstração e testes.
  <img src="https://raw.githubusercontent.com/pelinsarix/pelinsari_aws_ponderada/main/assets/default.png"/>

### Requisitos

- **PHP 7.4 ou superior**: Linguagem de script utilizada para o desenvolvimento da aplicação.
- **MySQL**: Sistema de gerenciamento de banco de dados utilizado no Amazon RDS.
- **Servidor Web Apache ou Nginx**: Servidor para hospedar a aplicação PHP.

### Configuração do Servidor

1. **Instalação do Servidor Web**

   O servidor web (Apache ou Nginx) deve estar instalado na instância EC2. Para instalar o Apache, por exemplo, use o comando:

   ```bash
   sudo yum install httpd -y
   ```

   E para iniciar o servidor Apache:

   ```bash
   sudo service httpd start
   ```

2. **Configuração do PHP**

   Certifique-se de que o PHP está instalado e configurado para trabalhar com o servidor web. Para instalar o PHP:

   ```bash
   sudo yum install php php-mysql -y
   ```

3. **Configuração da Conexão com o Banco de Dados**

   - **Arquivo de Configuração**: O arquivo `dbinfo.inc` contém as informações necessárias para a conexão com o banco de dados RDS. Certifique-se de que as credenciais e o endpoint estão corretos.

4. **Deploy da Aplicação**

   Copie os arquivos PHP para o diretório do servidor web:

   ```bash
   sudo cp /caminho/para/seus/arquivos/*.php /var/www/html/
   ```

   Certifique-se de que os arquivos têm as permissões corretas para serem acessados pelo servidor web.

### Executando o Projeto

Para rodar a aplicação:

1. Acesse a URL pública da instância EC2 no seu navegador.
2. Navegue até a página `jogadores_futebol.php` para interagir com a aplicação e gerenciar os dados dos jogadores.

## Contato

Para mais informações ou dúvidas, entre em contato com o desenvolvedor através do email [gabriel.ribeiro@sou.inteli.edu.br](mailto:gabriel.ribeiro@sou.inteli.edu.br).
