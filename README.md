## Transfer Webpack Plugin For Angular Template File

Transfer files to the build directory

### Getting started

Install the plugin:

```
npm install --save-dev angular-template-transfer-webpack-plugin
```


### API
```javascript
new AngularTemplateTransferWebpackPlugin(patterns: array, [basePath: string])
```

* `patterns` – array of patterns `{ from: 'path', to: 'path' }`, `from` – relative to `basePath` or to `context` of your config (if `basePath` is not exists), 
`to` – relative to the build directory
* `basePath` (optional) – directory to be resolved to `from` parameter

### Usage

named your template file by .template.html

```javascript
var AngularTemplateTransferWebpackPlugin = require('angular-template-transfer-webpack-plugin');

module.exports = {
    context: path.join(__dirname, 'app'),
    plugins: [
        new AngularTemplateTransferWebpackPlugin([
            { from: 'i18n', to: 'i18n' },
            { from: 'root' }
        ])
    ]
};

module.exports = {
    plugins: [
        new AngularTemplateTransferWebpackPlugin([
            { from: 'i18n', to: 'i18n' },
            { from: 'root' }
        ], path.join(__dirname, 'app'))
    ]
};
```
