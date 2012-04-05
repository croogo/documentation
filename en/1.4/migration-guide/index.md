# Migration Guide

It goes without saying that you should keep a fully backed-up copy of your
database and web directory.

- Check the [system requirement](../getting-started/requirements)

- `Config/core.php`

	If your site allows public registration, it's especially important if to 
	keep a copy of `Security.salt` and `Security.cipherSeed` values from the
	existing config/core.php file.

- `Config/database.php`

	The format of the database.php file is similar, with few differences:
	* 'driver' config key has been renamed to 'datasource'.
	* 'datasource' value requires a valid class name as dictated by CakePHP

- Plugin and themes compatibility

	Check that active plugins/themes have already provide a 1.4 compatible
	version. You might need to disable them prior to upgrading.

- CakePHP path
	If you are deploying using git, symlink CORE/lib/Cake in your APP directory.

The safest way to upgrade is by installing Croogo 1.4 in a separate directory,
and setup a separate virtual host using the new `webroot` folder as the vhost's
DocumentRoot.

Update the salts, cipherSeed and database settings as described above.

You are now set. Try browsing the your new vhost that is running with Croogo 1.4.

# Updating plugins

- You can use CakePHP **upgrade** shell to assist migrating your plugins, eg:

	``cake upgrade all --help``
	``cake upgrade all -p YourPlugin -g  # run this in your croogo directory``

	Plugin must be active to access its assets. This is enforced by CakePHP's
	plugin mechanism.

- Plugins now needs Config/plugin.json

- Admin menus are handled by ``CroogoNav`` class.