# Installation

Clone the latest version of Croogo 1.4, copy it into the /app folder of a
CakePHP 2 install, then upload all these files to your server.

### Folder permissions
CakePHP uses the _/app/tmp_ directory for a number of different operations.
Model descriptions, cached views, and session information are just a few
examples. As such, make sure the _/app/tmp_ directory in your cake installation
is writable by the web server user.  

Croogo also needs you to make _/app/Config_ writable so it can update config
files and to upload files through Croogo you need to make
`/app/webroot/uploads` writeable too.

### Web based installer

* Visit http://your-site.com/ from your browser and follow the instructions.

## Cloning the git repository

[Repository](http://github.com/croogo/croogo) contains 'app' directory only. You
need to upload CakePHP 2.0.x related files yourself. The default directory
structure of a working application is:

* app/ (only content of this directory is available in the Croogo repository)
* lib/
* plugins/
* vendors/
* .htaccess
* README
* index.php

Download latest version of CakePHP from here:
[http://github.com/cakephp/cakephp/downloads](http://github.com/cakephp/cakephp/downloads).