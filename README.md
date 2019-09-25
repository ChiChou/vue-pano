# vue-pano

**Looking for maintainers**

[![npm version][npm-image]][npm-url]

[中文文档](README.cn.md)

WebGL panorama component for vue.js

[![Screenshot](screen.png)](https://chichou.github.io/vue-pano/)

Click this link or scan the QRCode on your mobile devices to see the demo:

[![qrcode](qrcode.png)](https://chichou.github.io/vue-pano/)

## Usage

### The Component

Use npm or yarn to add `vue-pano` to your dependency. Following vue snippet intruduces the component to your view:

```javascript
<script>
import Pano from 'vue-pano'

...

export default {
  components: { Pano }
}
</script>
<template>
  <pano title="The Title" width="720" height="480" bundle="example/assets/pano/pantry/" format="jpg"></pano>
</template>
```

Use these props to define the texture and size:

- width, height: the size of the component
- title: the title
- bundle: base path for the six textures
- format: extension of the texture images, like `jpg`
- debug: boolean, is debugging

Currently I don't support higher customization or events handling, if you need so, feel free to issue that.

### Preparing the image

You can use [PhotoSphere App from Google](https://www.google.com/streetview/apps/) to take a panorama with a smartphone (both Android and iOS)! Since it results in a equirectangular projection skysphere image (only one rectangular), and the vue-pano only supports the skybox format (six squares), you need to convert the image using this tiny tool I wrote: [glskybox](https://github.com/ChiChou/glskybox).

![texture](texture.png)

If you are not satisified with the camera on mobile, or you need to take the picture indoor, you can follow the [instruction here (in Chinese)](https://blog.chichou.me/microsoft-ice-%E5%88%B6%E4%BD%9C%E5%85%A8%E6%99%AF%E7%85%A7%E7%89%87-af114142745d) about how to use the full frame camera with a wide angle lens, and compose these pictures into a panorama with [Microsoft ICE](http://research.microsoft.com/en-us/um/redmond/projects/ice/).

Here are some image stitching tool you can use to compsoe the panorama picture:

- [Microsoft ICE](http://research.microsoft.com/en-us/um/redmond/projects/ice/) (Free, Windows only)
- [ppwwyyxx/OpenPano](https://github.com/ppwwyyxx/OpenPano) (Open source, cross platform)
- [PTGui](https://www.ptgui.com/) (Paid, for Mac OSX and Windows)
- [Hugin](http://hugin.sourceforge.net/) (Open source, cross platform)
- [Auto Stitch](http://matthewalunbrown.com/autostitch/autostitch.html) (Offers both community version and professional version, supports Mac OSX and Windows)

The demo texture can be found under `example/assets/pano` directory.

## Contributing

If you want to contribute to the project, clone this repo adn run following commands for hosting a development server, or build for production.

``` bash
# install dependencies
yarn

# serve with hot reload at localhost:8080
yarn run dev

# build for production with minification
yarn run build
```

## TODO

- [ ] json bundle
- [ ] low quality preview background
- [ ] image progress bar

## License

MIT


[npm-image]: https://img.shields.io/npm/v/vue-pano.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/vue-pano
