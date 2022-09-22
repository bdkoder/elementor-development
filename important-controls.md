```php

$this->add_responsive_control(
    'columns',
    [
        'label'   => esc_html__('Columns', 'elementor-addons'),
        'type'    => Controls_Manager::SELECT,
        'options' => [
            1 => esc_html__('1 Column', 'elementor-addons'),
            2 => esc_html__('2 Columns', 'elementor-addons'),
            3 => esc_html__('3 Columns', 'elementor-addons'),
        ],
        'default'        => 2,
        'tablet_default' => 1,
        'mobile_default' => 1,
        // 'render_type'     => 'template',
        'selectors'       => [
            '{{WRAPPER}} .sa-post-list' => 'grid-template-columns: repeat({{SIZE}}, 1fr);',
        ],
    ]
);

$this->add_responsive_control(
    'column_gap',
    [
        'label'      => esc_html__('Column Gap', 'elementor-addons'),
        'type'       => Controls_Manager::SLIDER,
        'size_units' => ['px', 'em'],
        'range'      => [
            'px' => [
                'min' => 0,
                'max' => 50,
            ]
        ],
        'default' => [
            'unit' => 'px',
            'size' => 20,
        ],
        'selectors' => [
            '{{WRAPPER}} .sa-post-list' => 'grid-gap: {{SIZE}}{{UNIT}};',
        ],
    ]
);

$this->add_responsive_control(
    'img_width',
    [
        'label'      => esc_html__('Width', 'elementor-addons'),
        'type'       => Controls_Manager::SLIDER,
        'size_units' => ['px', 'em', '%'],
        'range'      => [
            'px' => [
                'min' => 50,
                'max' => 500,
            ],
            '%'  => [
                'min' => 0,
                'max' => 100,
            ],
        ],
        'selectors'  => [
            '{{WRAPPER}} .sa-post-img-wrapper' => 'min-width: {{SIZE}}{{UNIT}}; max-width: {{SIZE}}{{UNIT}};',
        ],
    ]
);

$this->add_responsive_control(
    'img_height',
    [
        'label'      => esc_html__('Height', 'elementor-addons'),
        'type'       => Controls_Manager::SLIDER,
        'size_units' => ['px', 'em'],
        'range'      => [
            'px' => [
                'min' => 50,
                'max' => 300,
            ],
        ],
        'selectors'  => [
            '{{WRAPPER}} .sa-post-img-wrapper' => 'min-height: {{SIZE}}{{UNIT}}; max-height: {{SIZE}}{{UNIT}};',
        ],
    ]
);

```

### Dimensions (Padding/Margin) Controls

```php

$this->add_responsive_control(
    'item_padding',
    [
        'label'      => esc_html__('Padding', 'elementor-addons'),
        'type'       => Controls_Manager::DIMENSIONS,
        'size_units' => ['px', 'em', '%'],
        'default'    => [
            'top'      => '1.5',
            'right'    => '1.5',
            'bottom'   => '1.5',
            'left'     => '1.5',
            'unit'     => 'em',
            'isLinked' => true,
        ],
        'selectors'  => [
            '{{WRAPPER}} .sa-post-item' => 'padding: {{TOP}}{{UNIT}} {{RIGHT}}{{UNIT}} {{BOTTOM}}{{UNIT}} {{LEFT}}{{UNIT}};',
        ],
    ]
);

```
### Border & Border Radius Controls

```php

$this->add_group_control(
    Group_Control_Border::get_type(),
    [
        'name' => 'item_border',
        'label' => esc_html__('Border', 'elementor-addons'),
        'fields_options' => [
            'border' => [
                'default' => 'solid',
            ],
            'width' => [
                'default' => [
                    'top' => '1',
                    'right' => '1',
                    'bottom' => '1',
                    'left' => '1',
                    'unit' => 'px',
                    'isLinked' => false,
                ],
            ],
            'color' => [
                'default' => '#eaeaea',
            ],
        ],
        'selector' => '{{WRAPPER}} .sa-post-item',
    ]
);

$this->add_responsive_control(
    'item_border_radius',
    [
        'label' => esc_html__('Border Radius', 'elementor-addons'),
        'type' => Controls_Manager::DIMENSIONS,
        'size_units' => ['px', 'em', '%'],
        'default' => [
            'top' => '.25',
            'right' => '.25',
            'bottom' => '.25',
            'left' => '.25',
            'unit' => 'em',
            'isLinked' => true,
        ],
        'selectors' => [
            '{{WRAPPER}} .sa-post-item' => 'border-radius: {{TOP}}{{UNIT}} {{RIGHT}}{{UNIT}} {{BOTTOM}}{{UNIT}} {{LEFT}}{{UNIT}}; overflow: hidden;',
        ],
    ]
);
```
### Customize background control

```php
$this->add_group_control(
    Group_Control_Background::get_type(),
    [
        'name' => 'main_background',
        'label' => esc_html__('Background', 'elementor'),
        'types' => ['classic', 'gradient'],
        'exclude' => ['image'],
        'fields_options' => [
            'background' => [
                'label' => esc_html__('New Label Here...', 'elementor'),
                'default' => 'classic',
            ],
            'color' => [
                'default' => '#fff',
            ],
        ],
        'selector' => '{{WRAPPER}} .class-name',
    ]
);
```

### Choose with selectors_dictionary

```php
$this->add_responsive_control(
    '_position',
    [
        'label'       => esc_html__('Position', 'elementor-addons'),
        'description' => esc_html__('description', 'elementor-addons'),
        'type'        => Controls_Manager::CHOOSE,
        'label_block' => false,
        'options'     => [
            'left' => [
                'title' => esc_html__('Left', 'elementor-addons'),
                'icon'  => 'eicon-h-align-left',
            ],
            'top' => [
                'title' => esc_html__('Top', 'elementor-addons'),
                'icon'  => 'eicon-v-align-top',
            ],
            'right' => [
                'title' => esc_html__('Right', 'elementor-addons'),
                'icon'  => 'eicon-h-align-right',
            ],
        ],
        'toggle'          => false,
        'desktop_default' => 'top',
        'tablet_default'  => 'top',
        'mobile_default'  => 'top',
        'prefix_class'    => 'class-name-%s-',
        'style_transfer'  => true,
        'selectors'       => [
            '{{WRAPPER}} .elementor-widget-container' => '{{VALUE}};',
        ],
        'selectors_dictionary' => [
            'left'  => 'flex-direction: row; text-align: left;',
            'top'   => 'flex-direction: column; text-align: left;',
            'right' => 'row-reverse; flex-direction: row-reverse; text-align: right;'
        ]
    ]
);

```
### Responsive Width

```php
$this->add_responsive_control(
    'width',
    [
        'label'           => esc_html__('Width', 'elementor-addons'),
        'type'            => Controls_Manager::SLIDER,
        'size_units'      => ['%', 'px'],
        'desktop_default' => [
            'unit' => '%'
        ],
        'tablet_default' => [
            'unit' => '%',
            'size' => 100
        ],
        'mobile_default' => [
            'unit' => '%',
            'size' => 100
        ],
        'range' => [
            '%' => [
                'min' => 1,
                'max' => 100,
            ],
            'px' => [
                'min' => 50,
                'max' => 1000,
            ],
        ],
        'selectors' => [
            '{{WRAPPER}} .class-name' => 'width: {{SIZE}}{{UNIT}};'
        ],
    ]
);

```

### Popover Toggle

```php
$this->add_control(
    'offset_toggle',
    [
        'label'        => esc_html__('Offset', 'elementor-addons'),
        'type'         => Controls_Manager::POPOVER_TOGGLE,
        'label_off'    => esc_html__('None', 'elementor-addons'),
        'label_on'     => esc_html__('Custom', 'elementor-addons'),
        'return_value' => 'yes',
    ]
);

$this->start_popover();

$this->add_responsive_control(
    'image_offset_y',
    [
        'label'      => esc_html__('Offset Top', 'elementor-addons'),
        'type'       => Controls_Manager::SLIDER,
        'size_units' => ['px'],
        'condition'  => [
            'offset_toggle' => 'yes'
        ],
        'range' => [
            'px' => [
                'min' => -1000,
                'max' => 1000,
            ],
        ],
        'selectors' => [
            '{{WRAPPER}} .class-name' => 'margin-top: {{SIZE}}{{UNIT}};',
        ],
    ]
);

$this->end_popover();

```
