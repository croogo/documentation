# Hooks

Hooks are ways plugins can integrate themselves to the whole application. They are set from the plugin's bootstrap file. Hooks are set using the [Croogo](http://github.com/croogo/croogo/blob/master/libs/croogo.php) class from bootstrap.

The code below assumes your plugin's name is **example**.

## Routes

The first thing a plugin may need to integrate with the whole application is it's routes for beautiful urls. The routes file for plugins is placed under app/plugins/example/config/example_routes.php.

Content of example_bootstrap.php:

    Croogo::hookRoutes('Example');

## Behavior

To hook your plugin's ExampleBehavior (at app/plugins/example/models/behaviors/example.php) to Node model:

    Croogo::hookBehavior('Node', 'Example.Example');

If you want the behavior to be attached to ALL models:

    Croogo::hookBehavior('*', 'Example.Example');

## Component

To hook your plugin's ExampleComponent (at app/plugins/example/controllers/components/example.php) in ALL controllers:

    Croogo::hookComponent('*', 'Example.Example');

If you want the component to be loaded only in NodesController:

    Croogo::hookComponent('Nodes', 'Example.Example');

## Helper

To hook your plugin's ExampleHelper (at app/plugins/example/views/helpers/example.php) in ALL controllers:

    Croogo::hookHelper('*', 'Example.Example');

If you want the helper to be loaded only in NodesController:

    Croogo::hookHelper('Nodes', 'Example.Example');

## Admin menu

Plugins may require to have their own navigation menu in admin panel. For that, you need to create an element under app/plugins/example/views/elements/admin_menu.ctp:

    <a href="#">Example</a>
    <ul>
        <li><a href="#">Link 1</a></li>
        <li><a href="#">Link 2</a></li>
    </ul>

Now add this line to the bootstrap:

    Croogo::hookAdminMenu('Example');

If the plugin is activated, you will see the links under **Extensions** menu in admin panel.

## Admin row action

When you visit **Content > List**, you will see a list in a table with a column named **Actions** on right having links like Edit and Delete. What if a plugin wanted to show another link beside them that performs something for that particular Node? That's what row action hooks are for:

    Croogo::hookAdminRowAction('Nodes/admin_index', 'Example', 'plugin:example/controller:example/action:index/:id');

The code above in bootstrap will generate a new link **Example** under the Actions column in **Content > List** page. And the link will point to /admin/example/index/123 where 123 is the Node ID.

## Admin tab

Form fields in Croogo are organized in groups and shown in tabs in admin panel. Plugins may sometimes require to extend the form by adding more fields when adding, for example, Nodes. For this, you need to have the form fields in an element first. Content of app/plugins/example/views/elements/admin\_tab\_node.ctp:

    <?php
        echo $form->input('example_field');
    ?>

Now in the plugin's bootstrap, we will add information so this element is hooked as a tab when adding and editing Nodes:

    Croogo::hookAdminTab('Nodes/admin_add', 'Example', 'example.admin_tab_node');
    Croogo::hookAdminTab('Nodes/admin_edit', 'Example', 'example.admin_tab_node');