# vue-barcodes-generator

[![npm](https://img.shields.io/npm/v/vue-barcodes-generator.svg?style=flat-square)](https://www.npmjs.com/package/vue-barcodes-generator)
[![npm](https://img.shields.io/npm/dt/vue-barcodes-generator.svg?style=flat-square)](https://www.npmjs.com/package/vue-barcodes-generator)
[![npm](https://img.shields.io/npm/dm/vue-barcodes-generator.svg?style=flat-square)](https://www.npmjs.com/package/vue-barcodes-generator)

This component creates a form to generate barcodes. This form includes the required 3 inputs (start number, barcode count, barcode number length ) and you can add additional inputs. This form creates barcodes with this inputs value when form is sumbitted. 

![](https://raw.githubusercontent.com/Alertis/vue-barcodes-generator/main/screenshots/app.png)


## Install
```
npm install vue-barcodes-generator
```

## Usage
#### 1. Add VueBarcodes as a component
```javascript
import VueBarcodes from 'vue-barcodes-generator'
new Vue({
  components: {
    'VueBarcodes': VueBarcodes
  }
})
```
#### 2. Create the varaibles
```javascript
data: function(){
    return{
      inputs: [
        {
            name: 'start',
            title: 'First Barcode No',
            val: 1
        },
        {
            name: 'count',
            title: 'Barcode Count',
            val: 10
        },
        {
            name: 'length',
            title: 'Number Length',
            val: 2
        },
      ],
      buttonText: 'Create',
    }
  }
```
#### 3. Use it
```html
  <VueBarcodes 
    :inputs="inputs"
    :buttonText="buttonText"
  />

```

## Props
|Props|Description|Required|Type|Default|
|-----|-----------|--------|----|-------|
|inputs|Components use this props for generate form|true|Array|`[{name: 'start', title: 'Start Number', val:1},{name: 'count', title: 'Barcode Count', val: 10}, {name: 'length', title: 'Number Length', val: 4}]`|
|buttonText|Title for button|true|String|`'Generate'`|
|buttonClass|Class name for button|false|String|-|
|barcodeConfig|Settings for barcode|false|Object|-|

### Inputs
This props type is Array and includes a element per form input. It has 3 required element and if you dont pass these elements, component generates with default value. You can generate unlimited inputs.

```javascript 
[
    {
        name: 'start',
        title: 'Start Number',
        val:1
    },
    {
        name: 'count',
        title: 'Barcode Count',
        val: 10
    },
    {
        name: 'length', 
        title: 'Number Length',
        val: 4
    }
]
```

If you want edit required 3 elements, you should add element same name (start, count, length)

<strong> name: </strong> unique name for input <br>
<strong> title: </strong> caption for input <br>
<strong> val: </strong> value for input


### barcodeConfig
This props type is Object and includes settings for generate barcode. This package uses  [JsBarcode](https://github.com/lindell/JsBarcode) library for generate barcode and you can inspect to [JsBarcode Documentation](https://github.com/lindell/JsBarcode/wiki/Options) for barcodeConfig props.
