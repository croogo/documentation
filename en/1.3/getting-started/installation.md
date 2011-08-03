# Installation

After [downloading the latest version](http://github.com/croogo/croogo/downloads), extract the zip archive and upload the content to your server.

**Permissions**: CakePHP uses the /app/tmp directory for a number of different operations. Model descriptions, cached views, and session information are just a few examples. As such, make sure the /app/tmp directory in your cake installation is writable by the web server user.

#### Web based installer

* Visit http://your-site.com/ from your browser and follow the instructions

#### Manual installation

* Create a new MySQL database (‘utf8_unicode_ci’ collation), and use these two SQL dump files in given order:
   * app/config/schema/sql/croogo.sql
   * app/config/schema/sql/croogo_data.sql
* Rename:
   * app/config/database.php.install to database.php, and edit the details.
   * app/config/settings.yml.install to settings.yml
* You can access your admin panel at http://your-site.com/admin. Login details below:
   * username: admin
   * password: password

It is recommended that you install Croogo using the web based installer for security reasons.

## Cloning the git repository

[Repository](http://github.com/croogo/croogo) contains 'app' directory only. You need to upload CakePHP 1.3 related files yourself. The default directory structure of a working application is:

* app/ (only content of this directory is available in the repository)
* cake/
* vendors/
* .htaccess
* index.php

Download latest version of CakePHP from here: [http://github.com/cakephp/cakephp/downloads](http://github.com/cakephp/cakephp/downloads).