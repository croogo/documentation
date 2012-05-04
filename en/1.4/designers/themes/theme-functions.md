# Theme functions

All theme specific functions (if you need any) go to
[CustomHelper](http://github.com/croogo/croogo/blob/1.4/View/Helper/CustomHelper.php).
If your theme alias is **MyTheme**, your CustomHelper should be placed in
`app/View/Themed/MyTheme/Helpers/CustomHelper.php`.

    <?php
    class CustomHelper extends Helper {

        public function myCustomMethod() {
            // code here
        }

    }

CustomHelper is automatically loaded, so you can use it like this your views
(.ctp files):

    $this->Custom->myCustomMethod();