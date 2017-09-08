# View Blocks

CakePHP view blocks have been implemented into Croogo 1.4 for `admin_index`,
`admin_add`, and `admin_edit`.

Read the CakePHP docs on view blocks:
[http://book.cakephp.org/2.0/en/views.html#using-view-blocks](http://book.cakephp.org/2.0/en/views.html#using-view-blocks).

You can override the default Croogo blocks:

    <?php
    $this->extend('/Common/admin_index');
    // Use assign for single line overrides
    $this->assign('title', 'My Custom Title');
    ?>
    <!-- Or start() and end() for multiline overrides -->
    <?php $this->start('tabs'); ?>
        <li>
            <?php echo $this->Html->link('My Link', '/somewhere'); ?>
        </li>
    <?php $this->end(); ?>

    <p>Any remaining content will override the content block.</p>

## admin\_index

The following blocks are available:

* `title`: Override the title.
* `tabs`: Override the li link tabs.
* `paging`: Override the pagination numbers and counter.

## admin\_edit / admin\_add

The following blocks are available:

* `title`: Override the title.
* `actions`: Override the li link actions.
* `buttons`: Override the Save and Cancel buttons.