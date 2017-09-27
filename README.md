# کد افزودن فیلد اضافی به صفحات
```
function add_custom_filed_to_page() {
    $id = Params::getParam("id");
    $page = Page::newInstance()->findByPrimaryKey($id);
    $page = json_decode(@$page['s_meta'], true);
    ?>
        <input type="text" name="meta[test]" value="<?php echo @$page['test']; ?>"> تست
        <input type="text" name="meta[test2]" value="<?php echo @$page['test2']; ?>">2 تست
    <?php
}
osc_add_hook('page_meta', 'add_custom_filed_to_page');
```
