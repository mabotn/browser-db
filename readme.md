A JavaScript library that simplifies the implementation of indexedDB

# Status

BrowserDB is currently an experimental project

# Example

The library is very simple to use

Call the `Database` function and specify both database and collection names

The `Find`, `Insert`, `Update` and `Delete` functions support both callbacks and promises

```javascript
import BrowserDB from 'browser-db'

BrowserDB("my-db", "people").then(async (db) => {
    let data = {
        firstName: "Mohamed Anas",
        lastName: "Ben Othman",
        country: "Tunisia"
    }

    let anas = await db.Insert(data)

    let result = await db.Find({ country: 'tunisia' }, { caseInsensitive: true, equalMatch: false })
    
    anas.age = 25
    anas = await db.Update(anas)
    await db.Delete(anas.id)
})
```

# License

BrowserDB is freely distributable under the terms of the [MIT license](https://github.com/mabotn/browser-db/blob/HEAD/LICENSE)

# Contributors

* [Mohamed Anas Ben Othman](mailto:mabo.tn@outlook.com)