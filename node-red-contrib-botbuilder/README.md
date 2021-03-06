# Node-RED

A Node-RED wrapper on top of [Microsoft Bot Builder](https://github.com/Microsoft/BotBuilder) Framework.

This node is part of project [node-red-contrib-viseo](https://github.com/NGRP/node-red-contrib-viseo) powered by [VISEO](http://www.viseo.com) Technologies.

Here is a [French Article](https://goo.gl/DMfJk1) on Bot Ecosystem and more.

## Quick Start

```
npm install node-red-contrib-viseo-botbuilder
```

## Documentation

| Node        | Description                                |
| ----------- |--------------------------------------------|
| Bot         | Microsoft BotBuilder Server                |
| Send Card   | Send a reply message to the user           |
| Luis        | Query MS LUIS and return first intent      |
| Event       | Handle bot's event like replies            |
| Profile     | Update user's profile from current message |
| FB Profile  | Update user's profile from facebook data   |
| FB Greeting | Set Messenger Greeting message             |
| FB Log      | Send custom events to Facebook analytics   |
| Attachement | Download message attachements              |

Configuration can be set in nodes or in a [configuration file](https://gist.github.com/JpEncausse/40a917ade2e044eb5c9f5a5381d886dc).
A configuration is easier to manage with multiple server. 
The absolute path to this file must be defined in ENV var `BOTBUILDER_CFG`. 

### Get Started

Here is a sample configuration to start you server. Switch will route to the convenient SendCard according to business logic. 

![Kickstart Nodes](https://github.com/NGRP/node-red-contrib-viseo/blob/master/node-red-contrib-botbuilder/doc/node_start.jpg?raw=true)

### Tips & Tricks

- The BotBuilder require an access to [Microsoft Bot Framework](https://dev.botframework.com/)
- A new HTTP server is started if config.json has been configured on port 3978 otherwise the Node-RED server is reused.
- An SSL certificate is required to work and must be declared in config.json OR node-red-config.js (depends if you start a new server)
- Users' storage is performed by any storage node like NeDB.

### Multilang

- The profile node handle the default locale
- The user's locale is defined throught MSBotBuilder priorities
- All fields of Card node are translated according to the user's locale
- Locales files are defined in `/data/locales/lang_country.json`

The JSON file can be generated from XLSX:

```
node path/to/xlsx2json.js path/to/input.xlsx path/to/output.json
```

## Getting Help

For further help, or general discussion, please use the [github issue tracker](https://github.com/NGRP/node-red-contrib-viseo/issues) and in order to be labeled with `question` tag please specify :
- Your message is a question / discussion
- The module or node name

## Contributing

Before raising a pull-request, please read our contributing guide.

This project adheres to the Contributor Covenant 1.4. By participating, 
you are expected to uphold this code. 
Please report unacceptable behavior to any of the project's core team.

## Authors

This project is a creation of [VISEO](http://www.viseo.com) Technology.

- Eric Brulatout [@ebrulato](https://twitter.com/ebrulato)
- Jean-Philippe Encausse [@jpencausse](https://twitter.com/jpencausse)
- Alice Vasseur [@Alice_Vasseur](https://twitter.com/Alice_Vasseur)

## Copyright and license

Copyright 2016-2017 [VISEO](http://www.viseo.com) under the Apache 2.0 license.