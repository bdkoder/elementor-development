### Post Render

```php
function render_image($image_id, $size) {
    $placeholder_image_src = Utils::get_placeholder_image_src();
    $image_src             = wp_get_attachment_image_src($image_id, $size);
    if (!$image_src) {
        printf('<img class="class-img" src="%1$s" alt="%2$s">', $placeholder_image_src, esc_html(get_the_title()));
    } else {
        print(wp_get_attachment_image(
            $image_id,
            $size,
            false,
            [
                'class' => 'class-img',
                'alt'   => esc_html(get_the_title())
            ]
        ));
    }
}
```

### Single Render

```php
print(wp_get_attachment_image(
        $image_id, //$settings['image']['id'],
        $size, //$settings['thumbnail_size'],
        false,
        [
            'class' => 'class-img',
            'alt'   => esc_html(get_the_title())
        ]
    ));
```

### Another Render way

```php
$thumb_url = Group_Control_Image_Size::get_attachment_image_src($item['image']['id'], 'thumbnail', $settings);
if (!$thumb_url) {
    printf('<img src="%1$s" alt="%2$s">', $item['image']['url'], esc_html($item['brand_name']));
} else {
    print(wp_get_attachment_image(
        $item['image']['id'],
        $settings['thumbnail_size'],
        false,
        [
            'alt' => esc_html($item['brand_name'])
        ]
    ));
}
```

### Alt Render

```php
Control_Media::get_image_alt($item['slider_image']);
```
