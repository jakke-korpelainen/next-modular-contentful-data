# next-modular-contentful-data

Helper for importing & exporting content for my [next-modular-contentful](https://github.com/jakke-korpelainen/next-modular-contentful) boilerplate.

## Contentful import and export

Modify the config files to your destination space (and source if you want to export).

### Installation

Install the contentful cli

`npm install -g contentful-cli`

### Import

In this repository root, run

`contentful space import --config import-config.json`

It will by default create the modular content types into your contentful space.

#### Example import config.json

https://github.com/contentful/contentful-export/blob/master/example-config.json

```json
{
  "spaceId": "source space id",
  "environmentId": "master",
  "managementToken": "destination space management token",
  "deliveryToken": "token to export both entries and assets from the Contentful Delivery API",
  "exportDir": "/path/to/export/directory",
  "saveFile": true,
  "contentFile": "export.json",
  "includeDrafts": false,
  "includeArchived": false,
  "skipContentModel": false,
  "skipContent": false,
  "skipRoles": false,
  "skipWebhooks": false,
  "contentOnly": false,
  "queryEntries": ["content_type=<content_type_id>", "sys.id=<entry_id>"],
  "queryAssets": ["fields.title=Example"],
  "downloadAssets": false,
  "host": "api.contentful.com",
  "proxy": "https://user:password@host:port",
  "rawProxy": false,
  "maxAllowedLimit": 1000,
  "limit": 25000,
  "errorLogFile": "/path/to/error.log",
  "useVerboseRenderer": false
}
```

### Export

If you'd like to fork and export your own space, you can do so.

`contentful space export --config export-config.json`

https://www.contentful.com/developers/docs/tutorials/cli/import-and-export/
