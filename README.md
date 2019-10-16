[![Latest Stable Version](https://poser.pugx.org/jonnitto/prettyembedaudio/v/stable)](https://packagist.org/packages/jonnitto/prettyembedaudio)
[![Total Downloads](https://poser.pugx.org/jonnitto/prettyembedaudio/downloads)](https://packagist.org/packages/jonnitto/prettyembedvimeo)
[![License](https://poser.pugx.org/jonnitto/prettyembedaudio/license)](https://packagist.org/packages/jonnitto/prettyembedvimeo)
[![GitHub forks](https://img.shields.io/github/forks/jonnitto/Jonnitto.PrettyEmbedAudio.svg?style=social&label=Fork)](https://github.com/jonnitto/Jonnitto.PrettyEmbedAudio/fork)
[![Support development](https://img.shields.io/badge/Donate-PayPal-yellow.svg)](https://www.paypal.me/Jonnitto/20eur)
[![My wishlist on amazon](https://img.shields.io/badge/Wishlist-Amazon-yellow.svg)](https://www.amazon.de/hz/wishlist/ls/2WPGORAVYF39B?&sort=default)  
[![GitHub stars](https://img.shields.io/github/stars/jonnitto/Jonnitto.PrettyEmbedAudio.svg?style=social&label=Stars)](https://github.com/jonnitto/Jonnitto.PrettyEmbedAudio/stargazers)
[![GitHub watchers](https://img.shields.io/github/watchers/jonnitto/Jonnitto.PrettyEmbedAudio.svg?style=social&label=Watch)](https://github.com/jonnitto/Jonnitto.PrettyEmbedAudio/subscription)
[![GitHub followers](https://img.shields.io/github/followers/jonnitto.svg?style=social&label=Follow)](https://github.com/jonnitto/followers)
[![Follow Jon on Twitter](https://img.shields.io/twitter/follow/jonnitto.svg?style=social&label=Follow)](https://twitter.com/jonnitto)

# Jonnitto.PrettyEmbedAudio

Prettier embeds for your Audio sources in [Neos CMS](https://www.neos.io)

| Version | Neos          |
| ------- | ------------- |
| 1.\*    | 3.3.\* + 4.\* |
| 2.\*    | ^4.2.\*       |

## Installation

Most of the time you have to make small adjustments to a package (e.g. configuration in `Settings.yaml`). Because of that, it is important to add the corresponding package to the composer from your theme package. Mostly this is the site packages located under `Packages/Sites/`. To install it correctly go to your theme package (e.g.`Packages/Sites/Foo.Bar`) and run following command:

```bash
composer require jonnitto/prettyembedaudio --no-update
```

The `--no-update` command prevent the automatic update of the dependencies. After the package was added to your theme `composer.json`, go back to the root of the Neos installation and run `composer update`. Et voilà! Your desired package is now installed correctly.

## FAQ

**What are the differences from the PrettyEmbed series to [Jonnitto.Plyr](https://github.com/jonnitto/Jonnitto.Plyr)?**

|                                    | PrettyEmbed series |  Plyr  |
| ---------------------------------- | :----------------: | :----: |
| YouTube Video                      |         ✓          |   ✓    |
| YouTube Playlist                   |         ✓          |        |
| Vimeo                              |         ✓          |   ✓    |
| Native Audio                       |         ✓          |   ✓    |
| Native Video                       |         ✓          |   ✓    |
| Advanced captions for native video |         ✓          |        |
| Preview image                      |         ✓          |        |
| Lightbox included                  |         ✓          |        |
| Preview image                      |         ✓          |        |
| Javascript API                     |                    |   ✓    |
| Filesize (JS & CSS)                |      smaller       | bigger |

All packages from the PrettyEmbed series have the benefit of a better frontend performance since the player gets only loaded on request. So, no iframe/video get's loaded until the user wants to watch a video or listen to audio.

## Customization

### Configuration

If you want to customize the default settings, take a look at the [Settings.Jonnitto.yaml](Configuration/Settings.Jonnitto.yaml#6) file. If no node property is giving, these default values will be taken. If you, for example, don't want to let the editor choose if the video should open in a lightbox you can deactivate the mixin in your Configuration folder like this:

```yaml
"Jonnitto.PrettyEmbedAudio:Content.Vimeo":
  superTypes:
    "Jonnitto.PrettyEmbedHelper:Mixin.Groups": true
```

These are the available mixins:

| Mixin name                                         | Description                                                           | Enabled |
| -------------------------------------------------- | --------------------------------------------------------------------- | :-----: |
| `Jonnitto.PrettyEmbedHelper:Mixin.Groups`          | Enables the inspector groups                                          |    ✓    |
| `Jonnitto.PrettyEmbedHelper:Mixin.IncludeAssets`   | Include the frontend resources                                        |    ✓    |
| `Jonnitto.PrettyEmbedHelper:Mixin.Muted`           | Whether the audio is muted upon loading, defaults to `false`          |         |
| `Jonnitto.PrettyEmbedHelper:Mixin.Loop`            | Loop the audio, defaults to `false`                                   |         |

If you want to give the editor even more control, you can also add your own properties like `color`, for example. For a full list look at the `defaults` section in the [Settings.Jonnitto.yaml](Configuration/Settings.Jonnitto.yaml#6) file.

### Fusion

If you want to use the player as a pure component, you can use the [`Jonnitto.PrettyEmbedAudio:Component.Audio`](Resources/Private/Fusion/Component/Audio.fusion) fusion prototype.

If you want to read the node properties and let the package handle all for you, you should use the [`Jonnitto.PrettyEmbedAudio:Content.Audio`](Resources/Private/Fusion/Content/Audio.fusion) prototype. For easier including in your own node types, you can disable the content element wrapping with `contentElement = false`. This is useful if you want to create for example a text with audio node type.
