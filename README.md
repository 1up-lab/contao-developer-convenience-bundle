ContaoDeveloperConvenienceBundle
--------------------------------
This bundle for Contao contains a set of tools that come in handy while developing with Contao.
Currently included commands:
1. `dev:sync <environment>`

   Synchronise Database and Files from a remote installation
2. `dev:imageoptim <environment>`

Requirements
-------------
This bundle needs a working [mage](https://github.com/1up-lab/Magallanes) configuration  (`mage.yml`)

### imageoptim

The `dev:imageoptim` command also requires a set of node.js modules.
Add them in your `package.json` file as shown below.
```
{
    "name": "...",
    "version": "...",
    [...]
    
    "dependencies": {
        [...]
        "imagemin": "^7.0.1",
        "imagemin-guetzli": "^3.0.0",
        "imagemin-mozjpeg": "^9.0.0",
        "imagemin-pngquant": "^9.0.0",
    [...]
```
Configuration
-------------
You can configure the image-optimization in your app's config (`app/config/config.yml`).
```YAML
developer_convenience:
    imageoptim:
        jpeg:
            quality: 85
        png:
            quality: 65-80
            speed: 7
```
>parameters are omittable. They default to above shown values.

`quality` parameters range in between `[1-100]`, where `100` results in the best quality.

`speed` parameter is only available for the png modules. This value ranges in between `[0-10]`, where `10` is the fastest (while decreasing quality).

License
-------

This bundle is under the MIT license. See the complete license in the bundle:

    Resources/meta/LICENSE

