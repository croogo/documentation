# YAML file

A theme.yml file is required for every theme in Croogo. This is required because themes can store useful information like menus and regions it uses, and this way it allows Croogo to query the database and make these information available to the theme without breaking MVC.

Content of an example theme.yml file at app/views/themed/my\_theme/webroot/theme.yml below:

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

* **name**: your theme's name
* **description**: your theme's description
* **screenshot**: a small preview of your theme placed under app/views/themed/my\_theme/webroot/img/screenshot.png
* **author**: your name
* **authorEmail**: your email
* **authorUrl**: your website
* **menus**: a list of menu aliases that the theme uses
* **regions**: a list of regions that the theme uses for showing blocks
* **vocabularies** (optional): a list of vocabulary aliases that the theme uses