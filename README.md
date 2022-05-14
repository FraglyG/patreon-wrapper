# Patreon Wrapper 🍊
An Simple Patreon Wrapper with much cleaner responses. Patreon. Why u do dis..

## Table of Contents
- [Installing](#installing)
- [Example](#example)
- [License](#license)

## Installing
Using NPM
```
$ npm install @anitrack/patreon-wrapper
```
Using YARN
```
$ yarn add @anitrack/patreon-wrapper
```

## Example

### Importing

CommonJS
```js
const { Patreon } = require('@anitrack/patreon-wrapper')
```
Typescript ES6
```js
import { Patreon } from '@anitrack/patreon-wrapper'
```

Authorization
```js
Patreon.Authorization({
    AccessToken: 'YOUR_API_V2_ACCESS_TOKEN',
    CampaignID: 'YOUR_CAPAIGN_ID',
})
```

### Fetching every Patrons on the Campaign

Promies then catch
```js
Patreon.FetchPatrons()
    .then((Patrons) => {
        // Handle Patrons List
        console.log(Patrons)
    })
    .catch((err) => {
        // Handle Error
        console.log(err)
    })
```
Async/Await
```js
var Patrons = await Patreon.FetchPatrons()

console.log(Patrons)
```

Clean Response Example
```js
 // Example response from fetching Patron list
 [
    {
      displayId: '12345678',
      displayName: 'Username',
      emailAddress: 'email@address.com',
      isFollower: false,
      subscription: {
        note: '',
        currentEntitled: {
          status: 'active_patron',
          tier: {
            id: '12345678',
            title: 'First Tier'
          },
          cents: 500, // 5 USD
          willPayCents: 500,
          lifetimeCents: 0,
          firstCharge: 'DATE',
          nextCharge: 'DATE',
          lastCharge: 'DATE'
        }
      },
      mediaConnection: {
        patreon: {
          id: '12345678',
          url: 'https://www.patreon.com/api/oauth2/v2/user/12345678'       
        },
        discord: {
          id: 'DISCORD_USER_ID',
          url: 'https://discordapp.com/users/DISCORD_USER_ID'
        }
      }
    },
    {
    ...
    },
    {
    ...
    },
    {
    ...
    }
]
```

## License

[MIT](LICENSE)
