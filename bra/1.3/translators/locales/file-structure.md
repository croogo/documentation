# File structure

For example, if you want to translate Croogo into Bengali (whose [ISO 639-2](http://www.loc.gov/standards/iso639-2/php/code_list.php) language code is **ben**), the file structure will be:

* app/locale/ben/
   * LC\_MESSAGES/
      * default.po

Best way to do it is by copying the [default.pot](http://github.com/croogo/locale/blob/master/default.pot) file, and then translating it using a software like [Poedit](http://www.poedit.net/). Do not forget to rename the .pot file as .po.