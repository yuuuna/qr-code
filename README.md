# QR-Code

Use HTML5 canvas draw QRCode

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API](#apu)
- [Support](#support)
- [Contributing](#contributing)

## Installation

```sh
npm install qr-code

// or

yarn add qr-code
```

## Usage
### Example 1
```js
import QrCode from "qr-code";

QrCodeModel.create('qrcode1', "Test123", {
    styleOptions: {
        fill: "#123456"
    },
    qrCodeOptions: {
        errorCorrectionLevel: "H"
    }
});
```
![Imgur](https://i.imgur.com/BSIQcUY.png)

### Example 2
```js
import QrCode from "qr-code";

QrCodeModel.create('qrcode1', "Puck go go", {
    styleOptions: {
        shape: 'roundedRect',
        fillType: 'linearGradient',
        fillGradient: {
            type: 'single',
            startPoint: {x: 0, y: 0},
            endPoint: {x: 300, y: 300},
            colorStops: [0, 'red', 1, 'green']
        }
    },
    qrCodeOptions: {
        errorCorrectionLevel: "H"
    }
});
```
![Imgur](https://i.imgur.com/cmyg8pb.png)




## API

### `create(elemelt, text, [options])`

#### `elemelt`
 * Type: String
 * Description: Id of div element

#### `text`
 * Type: String
 * Description: String to be converted to QR code

#### `options`
 * Type: [Object](#options)
 * Description: This is use to setting QR code options and style options. see [options](#options)

### Options

#### `qrCodeData`
Setting QR code transform options.

Please refer to [https://www.npmjs.com/package/qrcode#qr-code-options](https://www.npmjs.com/package/qrcode#qr-code-options).

#### `styleOptions`
Setting render QR code options.

##### `backgroundColor`
 * Type: String
 * Description: Color of background of QR code.
 * Default: "#FFFFFF" (Withe)

##### `fill`
 * Type: String
 * Description: Color of dark of QR code.
 * Default: "#000000" (Black)

##### `fills`
 * Type: String[]
 * Description: Color array of dark of QR code, Use to `fillRandom` fill type.
 * Default: ["#000000", "#252525", "#3e3e3e", "#434343"]

##### `fillType`
 * Type: Enum(`fill`, `linearGradient`, `circkeGradient`, `fillRandom`)
 * Description: fill type of dark of QR code.
    * `fill`: fill with a color.
    * `fillRandom`: Random fill with multi color. (You need set `fills`)
    * `linearGradient`: Fill linear gradient color. (You need set `fillGradient`)
    * `circkeGradient`: Fill radial gradient color. (You need set `fillGradient`)
 * Default: "fill"

##### `size`
 * Type: Integer
 * Description: QR code size, it will automatically fine-tune according to the actual situation.
 * Default: 300
 
##### `shape`
 * Type: Enum('rect', 'roundedRect', 'circle')
 * Description: Shape of drak of QR code.
 * Default: "rect"

##### `fillGradient`
 * Type: Object
    * `type`: "single" | "multi"
    * `startPoint`: {x: 0, y: 0}
    * `startRadius: 0
    * `endPoint`: {x: 0, y: 0}
    * `endRadius`: 0
    * `colorStops`: [0, 'red', 1, 'green']
 * Description: Fill gradient color options. see [Canvas Linear Gradient](https://www.w3schools.com/tags/canvas_createlineargradient.asp) and [Canvas Radial Gradient](https://www.w3schools.com/tags/canvas_createradialgradient.asp)
 * Default: 
 ```javascript
{
    type: 'single',
    startPoint: {x: 0, y: 0},
    startRadius: 0,
    endPoint: {x: 0, y: 0},
    endRadius: 0,
    colorStops: [0, 'red', 1, 'green']
}
```


## Support

Please [open an issue](https://github.com/puckwang/qr-code/issues/new) for support.

## Contributing

Please contribute using [Github Flow](https://guides.github.com/introduction/flow/). Create a branch, add commits, and [open a pull request](https://github.com/puckwang/qr-code/compare/).
