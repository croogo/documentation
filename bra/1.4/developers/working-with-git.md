# Working with Git

The git repository of Croogo is hosted at
[GitHub](http://github.com/croogo/croogo). The repository contains content of
the 'app' directory only so you need to
[download CakePHP](http://github.com/cakephp/cakephp/downloads) before cloning
it.

Once you have downloaded and extracted the archive of CakePHP, browse to the
'app' directory and empty it. Now run the following:

    $ cd app
    $ git init
    $ git remote add origin git://github.com/croogo/croogo.git
    $ git pull origin master
    $ git submodule update --init

## Contributing

The best way to contribute code to the core is by forking the repository on
GitHub, making changes, and then sending a pull request. To do this:

* Get yourself a [GitHub](http://github.com) account
* Fork [Croogo](http://github.com/croogo/croogo). 
* Then you will have your fork at http://github.com/yourusername/croogo. 
* Make any changes to it, and send a pull request.