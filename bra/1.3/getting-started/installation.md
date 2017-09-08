# Instalação

Após [download da última versão](http://github.com/croogo/croogo/downloads), extrair o zip do arquivo e enviar o conteúdo para seu servidor.

**Permissões**: CakePHP usa a pasta /app/tmp para um número de diferentes operações. Descrições do Model, cache das views, e informações da sessão são apenas alguns exemplos. Então, certifique-se que a pasta /app/tmp da sua instalação do cake, esteja editável pelo usuário do servidor web.

#### Instalador baseado na web

* Visite http://your-site.com.br/ pelo seu navegador e siga as instruções

#### Instalação Manual

* Criar um novo banco de dados MySQL (`utf8_unicode_ci`collaction), e use estes dois arquivos SQL dump na seguinte ordem:
   * app/config/schema/sql/croogo.sql
   * app/config/schema/sql/croogo_data.sql
* Renomeie:
   * app/config/database.php.install para database.php, e edite os detalhes.
   * app/config/settings.yml.install para settings.yml
* Você pode acessar seu painel administrativo em http://your-site.com/admin. Detalhes do Login abaixo:
   * username: admin
   * password: password

É recomendado que você instale o Croogo usando o instalador baseado na web por razões de segurança.

## Clonando o repositório git

[Repositório](http://github.com/croogo/croogo) contém somente a pasta 'app'. Você precisa enviar o CakePHP 1.3 para a mesma pasta. A estrutura padrão de diretórios da aplicação:

* app/ (o conteúdo desta pasta está disponível somente no repositório)
* cake/
* vendors/
* .htaccess
* index.php

Download da última versão do CakePHP aqui: [http://github.com/cakephp/cakephp/downloads](http://github.com/cakephp/cakephp/downloads).