[![license](https://img.shields.io/github/license/Leopotam/globals.svg)](https://github.com/Leopotam/globals/blob/develop/LICENSE.md)
# Globals support
[Github repo of globals support](https://github.com/Leopotam/globals).

## Service
Service locator pattern support.

### Common usage
```csharp
class PlayerSession {
    public int Rank;
}

// init instance.
Service<PlayerSession>.Set (new PlayerSession ());
// ...
// request instance.
Service<PlayerSession>.Get ().Rank = 10;
// ...
// cleanup.
Service<PlayerSession>.Set (null);
```

### Usage with automatic creation of instance
```csharp
class PlayerSession {
    public int Rank;
}

// request instance. if not exists - will be created through default constructor.
Service<PlayerSession>.Get(true).Rank = 10;
// ...
// cleanup.
Service<PlayerSession>.Set (null);
```

# License
The software released under the terms of the [MIT license](./LICENSE.md). Enjoy.

# Donate
Its free opensource software, but you can buy me a coffee:

<a href="https://www.buymeacoffee.com/leopotam" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>