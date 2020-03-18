<div align="center">

# griefergames

A high-level package for easily creating bots for the Minecraft network **GrieferGames.net**.

</div>

Built upon [mineflayer](https://github.com/PrismarineJS/mineflayer).

[Twitter](https://twitter.com/derjp_) |
[npm](https://www.npmjs.com/~derjp) |
[Forums](https://griefergames.de/index.php?user/6076-derjp/)

## Features

- Supports Promises/Async-Await
- Expressive API (type definitions)
- Easily connect on every "CityBuild" server using a single method
- Optimized chat queue - adapts to chat mode and other factors
- Session caching and refreshing
- Fake money filtering
- Useful events - react to private messages, money transfers etc.
- Make use of the complete feature set of Mineflayer - this package only adds functionality

## Installation

First clone the repository and go into directory.

```bash
$ git clone https://github.com/Dominic11/griefergames.git
$ cd griefergames
```

Install dependencies and compile using [TypeScript](https://www.typescriptlang.org/index.html#download-links).

```bash
$ npm install
$ tsc
```

Install the module in project.

```bash
$ cd ..
$ npm install --save ./griefergames
```

## Quick Start

Importing the package:

```javascript
const gg = require('griefergames');

// or (using destructuring)
const { createBot } = require('griefergames');

// or (using ES6 import)
import { createBot } from 'griefergames';
```

Creating a bot:

```javascript
const bot = createBot({
  username: 'email@example.com',
  password: 'password',
  cacheSessions: true,
  logMessages: true,
});

// This is async (returns a promise)
// We will ignore that for demonstration purposes.
bot.init();

bot.on('ready', () => {
  // You should wait for the 'ready' event
  // for most actions.
  console.log('Bot is now ready for use!');

  // For example, now would be a good time
  // to connect on our chosen "CityBuild" server.
  bot
    .connectCityBuild('cb2')
    .then(() => {
      console.log('Connected on CityBuild 2!');
      // Do things on the server...
    })
    .catch(e => {
      console.error(e);
    });
});
```

## Support

You will probably have some questions at some point of using this package.

The type definitions give away most of the functionality of the package. You can check these manually, or, if you are using an IDE with code suggestion functionality, such as IntelliSense, it will also list all available methods for you.
If you end up stuck though, don't hesitate to open a new issue directly on [GitHub](https://github.com/Dominic11/griefergames/issues)!

## License

[MIT](https://github.com/derjp/griefergames/blob/master/LICENSE)
