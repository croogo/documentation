# Estrutura de Arquivos

Um tema é identificado por um alias único. Se você tem seu tema na pasta app/views/themed/my\_theme, então o alias do seu tema é **my\_theme**.

O arquivo theme.yml é obrigatório. Você pode ver o arquivo YAML usado pelo tema padrão aqui [theme.yml](http://github.com/croogo/croogo/blob/master/webroot/theme.yml).

## Estrutura

Por exemplo, você tem um tema com o alias my_theme. Todos os arquivos devem ser colocados como isso:

* app/views/themed/my_theme/
   * elements/
   * helpers/
      * custom.php
   * layouts/
      * default.ctp
   * nodes/
      * view.ctp
   * …
   * webroot/
      * css/
         * theme.css
      * js/
         * theme.js
      * img/
         * screenshot.png
      * theme.yml

Não esqueça do arquivo theme.yml. Caso contrário, seu tema não estará disponível no painel administrativo.