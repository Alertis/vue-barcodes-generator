# vue-barcodes-generator

[![npm](https://img.shields.io/npm/v/vue-barcodes-generator.svg?style=flat-square)](https://www.npmjs.com/package/vue-barcodes-generator)
[![npm](https://img.shields.io/npm/dt/vue-barcodes-generator.svg?style=flat-square)](https://www.npmjs.com/package/vue-barcodes-generator)
[![npm](https://img.shields.io/npm/dm/vue-barcodes-generator.svg?style=flat-square)](https://www.npmjs.com/package/vue-barcodes-generator)

This component creates a form to generate barcodes. The form includes three required inputs (start number, barcode count, and barcode number length). Also, you can add some additional inputs to take into account while generating the barcode. After you have specified the related options, you can submit the form to generate barcodes.

![](https://raw.githubusercontent.com/Alertis/vue-barcodes-generator/main/screenshots/app.png)

## Install

```bash
npm install vue-barcodes-generator
```

## Usage

You can use the `vue-barcode-generator` package easily by following the three steps below:

#### 1. Add the `VueBarcodes` as a component

```javascript
import VueBarcodes from 'vue-barcodes-generator'
new Vue({
  components: {
    'VueBarcodes': VueBarcodes
  }
})
```

#### 2. Specify the barcode options

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

#### 3. Use the `VueBarcodes` component

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

This props type is `Array` and includes an element per form input. It has three required property and if you dont pass these elements, the component generates the default value. You can generate unlimited inputs.

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

If you want to edit three required elements, you should add the element with the same name (start, count, length) as below:

<strong> name: </strong> unique name for input <br>
<strong> title: </strong> caption for input <br>
<strong> val: </strong> value for input


### barcodeConfig

This props type is `Object` and includes settings for generating barcodes. This package uses the [JsBarcode](https://github.com/lindell/JsBarcode) library to generate barcodes and you can inspect to [JsBarcode Documentation](https://github.com/lindell/JsBarcode/wiki/Options) for barcodeConfig props.
