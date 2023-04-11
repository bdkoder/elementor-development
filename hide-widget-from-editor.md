### Hide widget from Editor Panel of Elementor

```php
global $elementor_widget_blacklist;

$elementor_widget_blacklist = [
    'heading',
    'your-widget'
];

add_filter('elementor/editor/localize_settings', function ($settings) {
    global $elementor_widget_blacklist;

    // uncomment to list all registered widgets, for debuging only
    // foreach ($settings['initial_document']['widgets'] as $key => $setting) {
    // 	var_dump($key);
    // }

    foreach ($elementor_widget_blacklist as $widget_name) {
        $settings['initial_document']['widgets'][$widget_name]['show_in_panel'] = false;
    }

    return $settings;
}, 99);

```

### Permanently Remove Widget

```php

$elementor_widget_blacklist = [
    'your-widget'
];

// Remove all the Elementor Free & Pro Widgets listed above
add_action('elementor/widgets/register', function ($widgets_manager) {
    global $elementor_widget_blacklist;
    foreach ($elementor_widget_blacklist as $widget_name) {
        $widgets_manager->unregister_widget_type($widget_name);
    }
}, 9999);
```
