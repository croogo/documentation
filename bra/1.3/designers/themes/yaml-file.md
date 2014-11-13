# Arquivo YAML

Um arquivo theme.yml é obrigatório a qualquer tema no Croogo. Ele é obrigatório porque temas podem armazenar informações úteis como menus e regiões, e desta forma permite o Croogo consultar o banco de dados e tornar estas informações disponíveis no tema sem quebrar o MVC.

O conteúdo de um arquivo theme.yml de exemplo, abaixo em app/views/themed/my\_theme/webroot/theme.yml:

    name: Sample
    description: Sample theme for Croogo
    screenshot: screenshot.png

    author: Author Name
    authorEmail: author@email.com
    authorUrl: http://authorswebsite.com

    menus:
      - main
      - footer

    regions:
      - left
      - right

    vocabularies:
      - categories
      - tags

* **name**: nome do seu tema
* **description**: descrição do seu tema
* **screenshot**: um pequena pré-visualização do seu tema, localizada em app/views/themed/my\_theme/webroot/img/screenshot.png
* **author**: seu nome
* **authorEmail**: seu email
* **authorUrl**: seu website
* **menus**: uma lista de alias de menus que seu tema usa
* **regions**: uma lista de regiões que o seu tema usa para exibir blocos
* **vocabularies** (opcional): uma lista de alias de vocabulário que o tema usa