# HuskyLens V2 for MakeCode

MakeCode extension library for DFRobot HuskyLens V2 AI Vision Sensor.

## Introduction

HuskyLens V2 is an easy-to-use AI vision sensor. It can learn to recognize objects, faces, colors, tags, QR codes, barcodes, and more. This MakeCode extension provides a complete interface to interact with HuskyLens V2 from micro:bit.

## Features

- **Multi-language Support**: Default English blocks with full localization support for Simplified Chinese (zh-cn) and Traditional Chinese (zh-tw)
- **UTF-8 Text Recognition**: Proper support for UTF-8 encoded text, including Chinese characters
- **Multiple AI Algorithms**:
  - Face Recognition
  - Object Recognition
  - Object Tracking
  - Object Classification
  - Self-learning Classification
  - Line Tracking
  - Color Recognition
  - Instance Segmentation
  - Gesture Recognition
  - Pose Recognition
  - License Plate Recognition
  - Text Recognition (OCR)
  - Emotion Recognition
  - Tag Recognition
  - QR Code Recognition
  - Barcode Recognition
  - Custom Model

## Installation

Add this extension to your MakeCode project:

1. Open [MakeCode for micro:bit](https://makecode.microbit.org/)
2. Click on "Extensions" in the settings menu
3. Search for `huskylensV2` or paste the GitHub repository URL
4. Click on the extension to add it to your project

Or add it directly in your project's `pxt.json`:

```json
{
  "dependencies": {
    "huskylensV2": "*"
  }
}
```

## Basic Usage

### Initialize HuskyLens V2

```blocks
huskylensV2.begin()
```

### Face Recognition Example

```blocks
huskylensV2.begin()
basic.forever(function () {
    huskylensV2.getResultFaceRecognition()
    if (huskylensV2.availableFaceRecognition()) {
        let id = huskylensV2.getCachedCenterFaceResult(huskylensV2.FaceProperty.ID)
        basic.showNumber(id)
    }
})
```

### Object Recognition Example

```blocks
huskylensV2.begin()
basic.forever(function () {
    huskylensV2.getResultObjectRecognition()
    if (huskylensV2.availableObjectRecognition()) {
        let count = huskylensV2.getCachedResultNumObject()
        basic.showNumber(count)
    }
})
```

### Text Recognition (OCR) Example

```blocks
huskylensV2.begin()
basic.forever(function () {
    huskylensV2.getResultTextRecogtion()
    if (huskylensV2.availableTextRecogtion()) {
        let name = huskylensV2.getCachedCenterTextResult(huskylensV2.TextProperty.Name)
        let content = huskylensV2.getCachedCenterTextResult(huskylensV2.TextProperty.Content)
        serial.writeLine("Name: " + name)
        serial.writeLine("Content: " + content)
    }
})
```

## Communication Methods

The library supports I2C communication with HuskyLens V2. Default I2C address is `0x32`.

## Language Support

- **English (en)**: Default language for all blocks
- **Simplified Chinese (zh-cn)**: 简体中文
- **Traditional Chinese (zh-tw)**: 繁體中文

The MakeCode editor will automatically display blocks in the appropriate language based on your editor settings.

## Text Recognition Features

- Supports UTF-8 encoded text, including Chinese characters
- Separate `Name` and `Content` fields for recognized text
- Optimized UTF-8 decoder for reduced code size (supports ASCII and 3-byte UTF-8 characters)

## License

MIT

Copyright (c) 2025, DFRobot

## Supported Targets

* for PXT/microbit


```package
huskylensV2=github:DFRobot-Embedded-Software/pxt-DFRobot_HuskyLensV2
```

## Links

- [DFRobot HuskyLens V2 Product Page](https://www.dfrobot.com/)
- [HuskyLens V2 Wiki](https://wiki.dfrobot.com/)
