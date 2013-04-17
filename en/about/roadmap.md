# Roadmap

## 1.5.x

* Plugin download/finder via shell (the CPM - package management idea)
* ~~Default theme: use Twitter Bootstrap~~ (default theme will not be changed)
* Admin theme: use Twitter Bootstrap here too? *in progress* **(aymeric and real34 - occitech)**
* Node Preview indicator, display published nodes that has preview flag set for admins.
* Defaults to InnoDb storage engine for mysql
* Plugin Activation ordering and presentation in plugin list
* Migration plugin (cakedc) can be use for installation, and plugins. create and update tables between versions, setup default/baseline data [http://croogo.lighthouseapp.com/projects/32818/tickets/258] *in progress* **(aymeric and real34 - occitech)**
* Helpers to create UI components markups, eg: tabs, accordion, panels.  Mostly for /admin *in progress* **(aymeric and real34 - occitech)**
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
