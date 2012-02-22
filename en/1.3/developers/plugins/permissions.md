# Plugin Permissions

To automatically add your controller and methods to the Permissions list inside Croogo and possibly set custom permissions during activation, you will use the addAco() method of the Croogo component. For example, if you have a plugin named *Acme* that has a controller named *acme_widgets* with *admin_index* and *add* methods, you would put something like this into the onActivation method of app/plugins/acme/config/acme_activation.php: 

	public function onActivation(&$controller) {
		$controller->Croogo->addAco('AcmeWidgets');
		$controller->Croogo->addAco('AcmeWidgets/admin_index');
		$controller->Croogo->addAco('AcmeWidgets/add', array('registered', 'public'));
	}

This populates the Users > Permissions page with the proper entries and automatically gives public and registered access to the add method.

**Note:** It is important to understand that the first parameter is the controller name and not the plugin name. As suggested by the [CakePHP plugin controllers documentation](http://book.cakephp.org/view/1113/Plugin-Controllers), your plugin controllers should have a unique name.

Likewise, to remove the ACL settings when the plugin is deactivated, simply do this:

	public function onDeactivation(&$controller) {
		$controller->Croogo->removeAco('AcmeWidgets');
	}

The [example plugin's activation file](http://github.com/croogo/croogo/blob/master/plugins/example/config/example_activation.php) can also be used as a guide for managing permissions during activation / deactivation.

For an overview of permissions in Croogo, see the [Administrator documentation regarding plugins](http://croogo.org/wiki/administrators/users/permissions).
