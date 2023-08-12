## Elementor Number Control

> [Back Home](../README.md)

To create a new control the Elementor plugin, you need to follow these steps:

![Section Preview](preview-1.png)

```php
// Include Elementor's Controls_Manager class
use Elementor\Controls_Manager;
```

### Text Control

```php
// Text Control
$this->add_control(
    'number',
    [
        'type'        => Controls_Manager::NUMBER,
        'label'       => __( 'Number', 'elementor-helper' ),
        'label_block' => false,
        'min' => 5,
        'max' => 100,
        'step' => 5,
        'default' => 10,
        'dynamic'     => [
            'active' => true,
        ]
    ]
);

```

### Render Output

```php
protected function render() {
    $settings = $this->get_settings_for_display();
    ?>
    
    <?php if(!empty($settings['number'])): ?>
        <div class="eh-number">
            <h1><?php echo $settings['number'] ?></h1>
        </div>
    <?php endif; ?>
    
    <?php
}
```

### Example Controls

```php
use Elementor\Controls_Manager;

// Other methods and control definitions...
protected function _register_controls() {
    $this->start_controls_section(
        'section_content',
        [
            'label' => esc_html__( 'Content', 'elementor-helper' ),
            'tab'   => Controls_Manager::TAB_CONTENT,
        ]
    );

    $this->add_control(
        'number',
        [
            'type'        => Controls_Manager::NUMBER,
            'label'       => __( 'Number', 'elementor-helper' ),
            'label_block' => false,
            'min' => 5,
            'max' => 100,
            'step' => 5,
            'default' => 10,
            'dynamic'     => [
                'active' => true,
            ]
        ]
    );

    $this->end_controls_section();
}
// Other methods and class implementation...

```

> [Back Home](../README.md)
