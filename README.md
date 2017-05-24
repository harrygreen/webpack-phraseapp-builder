# Webpack PhraseAppBuilder Plugin

Webpack plugin for generating translations files from PhraseApp.
This plugin uses the download API endpoint from PhraseApp, for further information please see the following [link](https://phraseapp.com/docs/api/v2/locales/#download)

## Usage

In your `webpack.config.js`

```javascript
var PhraseAppBuilderPlugin = require('webpack-pharseapp-builder');

module.exports = {
    // ...
    plugins: [
      new PhraseAppBuilderPlugin({
        localesId: ['someLocaleId'],  // Get the locales id from PhraseApp, you can add many ids
        accessToken: 'theAccesTokenId',  // Get your accessToken from PhraseApp
        projectId: 'theProjectId', // Get the project id from PhraseApp
        format: 'json' // specify the format from Pharseapp
      })
    ]
};
```

This will generate translations files in your configured output directory, for example:

```json
// build/es.json

{
  "some.key": "hello",
}
```

**Options:**

* `localesId`: The locales id from your PhraseApp project.
* `accessToken`: The accessToken to authorize the PhraseApp API.
* `projectId`: The project id from PhraseApp from where you want to extract your translations
* `format`: The format to download the translations
