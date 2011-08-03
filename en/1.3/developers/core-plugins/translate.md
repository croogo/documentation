# Translate

Translate plugin is one of the core plugins that is shipped with Croogo. If your website requires content in multiple languages (i18n), just activate it and you start translating right from your admin panel. 

Once active, you will see a **Translate** link under 'Actions' column where Edit and Delete links are present.

By default, it takes care of translations for these models:

* **Node**
* **Block**
* **Link**

## Configuration

Configuration for this at /app/plugins/translate/config/translate_bootstrap.php looks like this:

    Configure::write('Translate.models', array(
        'Node' => array(
            'title' => 'titleTranslation',
            'excerpt' => 'excerptTranslation',
            'body' => 'bodyTranslation',
        ),
        'Block' => array(
            'title' => 'titleTranslation',
            'body' => 'bodyTranslation',
        ),
        'Link' => array(
            'title' => 'titleTranslation',
            'description' => 'descriptionTranslation',
        ),
    ));

Now if you want your contact forms to be translated too, just add **Contact** model's name to the plugin's bootstrap like this:

    Configure::write('Translate.models', array(
        'Node' => array(
            'title' => 'titleTranslation',
            'excerpt' => 'excerptTranslation',
            'body' => 'bodyTranslation',
        ),
        'Block' => array(
            'title' => 'titleTranslation',
            'body' => 'bodyTranslation',
        ),
        'Link' => array(
            'title' => 'titleTranslation',
            'description' => 'descriptionTranslation',
        ),
        'Contact' => array(
            'title' => 'titleTranslation',
            'body' => 'bodyTranslation',
        ),
    ));