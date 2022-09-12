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
