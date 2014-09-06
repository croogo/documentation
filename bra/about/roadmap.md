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
* Replace Email Component with CakeEmail and move to models
* Move functionality in NodesController to the model
* Move CommentsController::add() functionality to model
* Move AttachmentsController::admin_add functionality to model
* Move non-controller CroogoComponent functionality to a Lib
* ~~Pluginify User management (extract as plugin)~~ **(rchavik)**
* Allow integration of third party auth, eg: twitter oauth, facebook, ldap,
* ~~Replace Config/settings.yml to Config/settings.json, remove spyc from Vendor~~ **(rchavik)**

## 2.0.x

* Fully Pluginize: Croogo can become a set of plugins and a minimalist app that simply installs the default plugin set for easy installation.
* Add namespaces
* PSR-0 and PSR-1 Compat
* Use composer.json instead of Config/plugin.json for extensions
* Offer RESTful API by core, to allow easy integration with third-party apps (could be an iPhone app too)
* Allow admins to update Croogo from admin panel (HTTP download, or backed by Git?)
* ~~Granular ACL~~ **(rchavik)**
* [Plugin] Contents: Nodes going out, forming a Contents plugin.
