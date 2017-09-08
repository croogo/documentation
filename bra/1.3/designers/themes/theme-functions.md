# Funções do Tema

Todas as funções específicas do tema (se você precisar de alguma) está em [CustomHelper](http://github.com/croogo/croogo/blob/master/views/helpers/custom.php).  Se o alias do seu tema é **my\_theme**, seu CustomHelper deveria ser colocado em app/views/themed/my\_theme/helpers/custom.php.

    <?php
    class CustomHelper extends Helper {
    
        public function myCustomMethod() {
            // code here
        }
    
    }
    ?>

CustomHelper é automaticamente carregado, então você pode usar isso desta forma em suas views (arquivos .ctp):

    $this->Custom->myCustomMethod();