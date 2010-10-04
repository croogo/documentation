# Theme functions

All theme specific functions (if you need any) go to [CustomHelper](http://github.com/croogo/croogo/blob/master/views/helpers/custom.php). If your theme alias is **my\_theme**, your CustomHelper should be placed in app/views/themed/my\_theme/helpers/custom.php.

    <?php
    class CustomHelper extends Helper {
    
        public function myCustomMethod() {
            // code here
        }
    
    }
    ?>

CustomHelper is automatically loaded, so you can use it like this your views (.ctp files):

    $this->Custom->myCustomMethod();