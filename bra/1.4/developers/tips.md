# Tips

## Make it faster

Croogo is shipped with debug level 1 enabled. You can disable it in
`/app/Config/croogo.php` to make it faster. Replace
[line 37](https://github.com/croogo/croogo/blob/1.4/Config/croogo.php.install#L35)
with this:

    Configure::write('debug', 0);
