# YAML file

A plugin.yml file is required for every plugin in Croogo that requires to be activated from admin panel. It stores useful information like the developer's contact details, as well as information on it's dependencies.

If your plugin's name is **example**, the content of [plugin.yml](http://github.com/croogo/croogo/blob/master/plugins/example/config/plugin.yml) file at app/plugins/examples/config/plugin.yml could be:

    name: Example
    description: Example plugin for demonstrating hook system

    author: Author Name
    authorEmail: author@example.com
    authorUrl: http://example.com

    dependencies:
      plugins:
        - acl
        - extensions

* **name**: your plugin's name
* **description**: your plugin's description
* **author**: your name
* **authorEmail**: your email address
* **authorUrl**: your website
* **dependencies** (optional): list of other plugins that this plugin depends on