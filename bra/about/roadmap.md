# Roadmap

## 1.5.x

* Plugin download/finder via shell (the CPM - package management idea)
* ~~Tema padrão: usa Twitter Bootstrap~~ (Tema padrão não sserá alterado)
* Tema Admin: usa Twitter Bootstrap também? *em desenvolvimento* **(aymeric and real34 - occitech)**
* Indicador de pré-visualização de Node, mostra nodes publicados com a flag de pré-visualização marcado pelos admins.
* Padrão InnoDb para mecanismo de armazenamento para mysql
* Ordenação da Ativação de Plugin e apresentação na lista de plugin
* Plugin Migration (cakedc) pode ser usado para instalação, e de plugins. Criar e atualizar tabelas entre versões, configurar dados padrão/base [http://croogo.lighthouseapp.com/projects/32818/tickets/258] *em desenvolvimento* **(aymeric and real34 - occitech)**
* Helpers para criar marcações para componentes UI, ex: tabs, accordion, panels.  Principalmente para /admin *em desenvolvimento* **(aymeric and real34 - occitech)**
* ~~Pluginify the File Manager, add better folder security~~ **(shama)**
* ~~Pluginify Blocks~~ **(shama)**
* ~~Pluginify Taxonomy~~ **(shama)**
* Trocado Email Component com CakeEmail e movido para model
* Movido funcionalidade em NodesController para o model
* Movido funcionalidade CommentsController::add() para model
* Movido funcionalidade AttachmentsController::admin_add para model
* Movido funcionalidade sem controller CroogoComponent para uma Lib
* ~~Pluginify User management (extraído como plugin)~~ **(rchavik)**
* Permitido integração de autenticação de terceiros, eg: twitter oauth, facebook, ldap,
* ~~Trocado Config/settings.yml para Config/settings.json, removido spyc do Vendor~~ **(rchavik)**

## 2.0.x

* Fully Pluginize: Croogo pode tornar-se um conjunto de plugins e um aplicativo minimalista que simplesmente instala o conjunto de plugins padrão para fácil instalação.
* Adicionado namespaces
* Compatível PSR-0 e PSR-1
* Use composer.json em vez de Config/plugin.json para extensões
* Oferece RESTful API por core, para permitir a fácil integração com aplicativos de terceiros ( pode ser uma aplicação iPhone também )
* Permite admins atualizar o Croogo pelo painel admin (HTTP download, ou pelo Git?)
* ~~Granular ACL~~ **(rchavik)**
* [Plugin] Contents: Nodes going out, forming a Contents plugin.
