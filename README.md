# Globals support
Globals pattern implementation (service locator).

> Tested on unity 2020.3 (not dependent on it) and contains assembly definition for compiling to separate assembly file for performance reason.

# Table of content
* [Socials](#socials)
* [Installation](#installation)
    * [As unity module](#as-unity-module)
    * [As source](#as-source)
* [Classes](#classes)
    * [Service](#service)
* [License](#license)

# Socials
[![discord](https://img.shields.io/discord/404358247621853185.svg?label=enter%20to%20discord%20server&style=for-the-badge&logo=discord)](https://discord.gg/5GZVde6)

## As unity module
This repository can be installed as unity module directly from git url. In this way new line should be added to `Packages/manifest.json`:
```
"com.leopotam.globals": "https://github.com/Leopotam/globals.git",
```
By default last released version will be used. If you need trunk / developing version then `develop` name of branch should be added after hash:
```
"com.leopotam.globals": "https://github.com/Leopotam/globals.git#develop",
```

## As source
If you can't / don't want to use unity modules, code can be downloaded as sources archive from `Releases` page.

# Classes

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
The software is released under the terms of the [MIT license](./LICENSE.md).

No personal support or any guarantees.