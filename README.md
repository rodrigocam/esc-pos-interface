## To generate a new jar release use `gradle fatJar`

## Usage example:


### Template
```xml
<document code-page="CP850">
    <line id="title" align="center" font="dh_dw_emphasized" cut="part" feed="3">
        <text>Gold Penny</text>
    </line>
    <line id="product" align="center" font="dw_emphasized" cut="part" feed="1">
        <text>Invalid</text>
    </line>
    <line id="price" align="center" font="emphasized" cut="part" feed="2">
        <text>0.0</text>
    </line>
    <line id="date" align="center" font="regular" cut="part" feed="1">
        <text>
            None
        </text>
    </line>
    <line id="info" align="center" font="regular" cut="part" feed="4">
        <text>Testing</text>
    </line>
</document>
```
### Code
```java
    /* EscPos driver to parse xml template to esc/pos commands */
    private EscPosDriver escPosDriver;

    /* XML Template with the print template */
    private InputStream xmlFile;
    
    this.escPosDriver = new EscPosDriver(this.xmlFile);
    this.escPosDriver.setTemplateText("product", "Beer");
    
    sendProductToPrint(this.escPosDriver.getBytes());
```
