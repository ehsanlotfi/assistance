## wp-string_replace_site

```
add_filter(  'gettext',  'string_replace_site'  );
add_filter(  'ngettext',  'string_replace_site'  );
function string_replace_site( $translated ) {
    $words = array(
        // 'word to translate' => 'translation'
    );
    $translated = str_ireplace(  array_keys($words),  $words,  $translated );
    return $translated;
}
```
