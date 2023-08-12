## Elementor Text Control

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
    'title',
    [
        'type'        => Controls_Manager::TEXT,
        'label'       => __( 'Title', 'elementor-helper' ),
        'label_block' => true,
        'dynamic'     => [
            'active' => true,
        ]
    ]
);

// add parameter for placeholder
'placeholder' => __( 'Type your title here', 'elementor-helper' ),

// add parameter for default value
'default' => __( 'Default title', 'elementor-helper' ),
```

### Render Output

```php
protected function render() {
    $settings = $this->get_settings_for_display();
    ?>
    
    <?php if(!empty($settings['title'])): ?>
        <div class="eh-title">
            <h1><?php echo $settings['title'] ?></h1>
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
        'title',
        [
            'type'        => Controls_Manager::TEXT,
            'label'       => __( 'Title', 'elementor-helper' ),
            'label_block' => true,
            'dynamic'     => [
                'active' => true,
            ]
        ]
    );

    // Label false
    $this->add_control(
        'title_2',
        [
            'type'        => Controls_Manager::TEXT,
            'label'       => __( 'Title', 'elementor-helper' ),
            'label_block' => false,
            'dynamic'     => [
                'active' => true,
            ]
        ]
    );

    // With Placeholder
    $this->add_control(
        'title_3',
        [
            'type'        => Controls_Manager::TEXT,
            'label'       => __( 'Title with placeholder', 'elementor-helper' ),
            'placeholder' => __( 'Type your title here', 'elementor-helper' ),
            'label_block' => true,
            'dynamic'     => [
                'active' => true,
            ]
        ]
    );

    // With Default
    $this->add_control(
        'title_4',
        [
            'type'        => Controls_Manager::TEXT,
            'label'       => __( 'Title with default', 'elementor-helper' ),
            'default'     => __( 'Default title', 'elementor-helper' ),
            'placeholder' => __( 'Type your title here', 'elementor-helper' ),
            'label_block' => true,
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
