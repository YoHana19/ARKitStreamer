# ARKit Streamer

A remote debugging tool for AR Founndation (tested on `3.1.0-preview.1`) with ARKit3 featrues.  

![img](https://i.imgur.com/vZoYIs1.gif)  

![Imgur](https://imgur.com/tQbJ1Sl.gif)  

## Environments

- Unity 2019.2 or more
- iPhone X or more

## Supporting ARKit features

- Depth
- Face (You have to modify ar-foundation's code a bit. [See issee #2](https://github.com/asus4/ARKitStreamer/issues/2))

## Install

- This depends on NDI (Network Device Interface), download and install NDI SDK for iOS from [https://ndi.tv/sdk/](https://ndi.tv/sdk/)

- This supports Unity Package Manager. Open the file `Packages/manifest.json` and add following lines into `scopedRegistries` and  `dependencies` section.

```json
{
  "scopedRegistries": [
    {
      "name": "npm",
      "url": "https://registry.npmjs.com",
      "scopes": [
        "jp.keijiro",
        "com.koki-ibukuro"
      ]
    }
  ],
  "dependencies": {
    "com.koki-ibukuro.arkitstream": "0.2.0",
    ...// other dependencies
  }
}
```

## How to Use

### Set up Sender iPhone

Download this reposidoty and install on iPhone. Then run the app on iPhone. Currentry following 2 features are supported.  

- Human Segmentation
- Face mesh  

Or you can simply add `ARKitSender` to your custom ARKit scene.  
![Imgur](https://imgur.com/tevPT1n.png)

Recomend using USB connected network instead of Wi-Fi to reduce network delay.  
![Imgur](https://imgur.com/4YVbIUP.png)

__NOTE__  
From __macOS 10.5 Catalina__ , NDI SDK installed path have been changed. See [KlakNDI](https://github.com/keijiro/KlakNDI/pull/44/files) to fix it.

### Simurate on Editor

Add `ARKitReceiver` to the scene which you want to simuirate on Editor. If sender-iPhone app is running, you can select the NDI source name. also confirm the iPhone's IP Address and port are correct.

![Imgur](https://imgur.com/u10iUBc.gif)

For more infomation, please check Assets/Sample directory.

## Libraries

- [KlakNDI](https://github.com/keijiro/KlakNDI/)
- [websocket-sharp](https://github.com/sta/websocket-sharp/)
