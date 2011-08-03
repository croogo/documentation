# Permissions

Croogo uses CakePHP's ACL for managing user permissions. To be honest, it can be very complicated to understand ACL for beginners. But Croogo takes the pain away by providing a simple and usable interface for managing permissions.

Since the application is built with a MVC framework, any url (other than normal files like CSS and images) you access is the output of a Controller's action. For example, when you visit a 'Hello World' blog post, it shows **Nodes** controller's **view** action.

Now to manage permissions for that action:

* Log in to your admin panel
* Go to **Users &gt; Permissions** page
* Click **Nodes**, it will then show all it's actions
* Then click on the tick/cross icon of **view** row to enable or disable access to that action for roles.