# Routes

From [book.cakephp.org](http://book.cakephp.org/view/945/Routes-Configuration): Routing is a feature that maps URLs to controller actions. It was added to CakePHP to make pretty URLs more configurable and flexible. Using Apache’s mod_rewrite is not required for using routes, but it will make your address bar look much more tidy.

If you have a plugin named **example**, your routes file will be placed at app/plugins/example/config/example_routes.php:

    Router::connect('/example/route/here', array(
        'plugin' => 'example',
        'controller' => 'example',
        'action' => 'index',
    ));

When you visit http://yoursite.com/example/route/here, CakePHP will map it to ExampleController's index method.