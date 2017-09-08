# Tips

## Make it faster

Since Croogo is still in beta, it is shipped with debug level enabled. You can disable it in /app/config/core.php to make it faster. Replace [line 37](http://github.com/croogo/croogo/blob/master/config/core.php#L37) with this:

    Configure::write('debug', 0);
