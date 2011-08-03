# Content types

By default, there are three content types:

* **Page**: for pages
* **Blog**: for blog posts
* **Node**: unless you are sure of what content type to use

If you think you require a new content type, you are able to create one from admin panel.

## Parameters

When you add or edit content types, you will notice a 'Params' field where you can enter parameters. It is expected that one parameter is entered per line with a key/value pair using equal sign as a separator. Example below:

    my_param_key=value_here
    another_key=another_value

Supported parameter keys for content types:

* **nodes\_per\_page**: Pagination limit for nodes

You are free to use more keys for parameters and they will be available in a nice formatted way by [ParamsBehavior](http://github.com/croogo/croogo/blob/master/models/behaviors/params.php).