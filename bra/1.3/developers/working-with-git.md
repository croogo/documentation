# Trabalhando com Git

O repositório git do Croogo está em [GitHub](http://github.com/croogo/croogo). O repositório contém apenas o conteúdo da pasta 'app', então antes você precisa clonar isto [download CakePHP](http://github.com/cakephp/cakephp/downloads).

Uma vez que você tenha baixado e descompactado o arquivo do CakePHP, navegue para a pasta 'app' e esvazie ela. Agora, execute o seguinte:

    $ cd app
    $ git init
    $ git remote add origin git://github.com/croogo/croogo.git
    $ git pull origin master
    $ git submodule init
    $ git submodule update

## Contribuindo

A melhor forma de contribuir com o código do core, é fazendo um forking do repositório no Github, fazendo alterações, e então enviando um pull request. Para fazer isso:

* Crie um conta no [GitHub](http://github.com) 
* Fork [Croogo](http://github.com/croogo/croogo). 
* Então você terá um fork em http://github.com/seuusername/croogo. 
* Faça qualquer alteração, e envie um pull request.