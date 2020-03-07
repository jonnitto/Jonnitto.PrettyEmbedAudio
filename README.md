[![Latest stable version]][packagist] [![Total downloads]][packagist] [![License]][packagist] [![GitHub forks]][fork] [![GitHub stars]][stargazers] [![GitHub watchers]][subscription] [![GitHub followers]][followers] [![Follow Jon on Twitter]][twitter]

# Jonnitto.PrettyEmbedAudio

Prettier embeds for your Audio sources in [Neos CMS]

## Installation

Most of the time you have to make small adjustments to a package (e.g. configuration in `Settings.yaml`). Because of that, it is important to add the corresponding package to the composer from your theme package. Mostly this is the site packages located under `Packages/Sites/`. To install it correctly go to your theme package (e.g.`Packages/Sites/Foo.Bar`) and run following command:

```bash
composer require jonnitto/prettyembedaudio --no-update
```

The `--no-update` command prevent the automatic update of the dependencies. After the package was added to your theme `composer.json`, go back to the root of the Neos installation and run `composer update`. Et voilà! Your desired package is now installed correctly.

## FAQ

**What are the differences from the PrettyEmbed series to [Jonnitto.Plyr]?**

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

If you want to customize the default settings, take a look at the [Settings.Jonnitto.yaml] file. If no node property is giving, these default values will be taken. If you, for example, don't want to let the editor choose if the video should open in a lightbox you can deactivate the mixin in your Configuration folder like this:

```yaml
'Jonnitto.PrettyEmbedAudio:Content.Audio':
  superTypes:
    'Jonnitto.PrettyEmbedHelper:Mixin.Loop': true
```

These are the available mixins:

| Mixin name                                       | Description                         | Enabled |
| ------------------------------------------------ | ----------------------------------- | :-----: |
| `Jonnitto.PrettyEmbedHelper:Mixin.Groups`        | Enables the inspector groups        |    ✓    |
| `Jonnitto.PrettyEmbedHelper:Mixin.IncludeAssets` | Include the frontend resources      |    ✓    |
| `Jonnitto.PrettyEmbedHelper:Mixin.Loop`          | Loop the audio, defaults to `false` |         |

### Fusion

If you want to use the player as a pure component, you can use the [`Jonnitto.PrettyEmbedAudio:Component.Audio`] Fusion prototype.

If you want to read the node properties and let the package handle all for you, you should use the [`Jonnitto.PrettyEmbedAudio:Content.Audio`] prototype. For easier including in your own node types, you can disable the content element wrapping with `contentElement = false`. This is useful if you want to create for example a text with audio node type.

[packagist]: https://packagist.org/packages/jonnitto/prettyembedaudio
[latest stable version]: https://poser.pugx.org/jonnitto/prettyembedaudio/v/stable
[total downloads]: https://poser.pugx.org/jonnitto/prettyembedaudio/downloads
[license]: https://poser.pugx.org/jonnitto/prettyembedaudio/license
[github forks]: https://img.shields.io/github/forks/jonnitto/Jonnitto.PrettyEmbedAudio.svg?style=social&label=Fork
[github stars]: https://img.shields.io/github/stars/jonnitto/Jonnitto.PrettyEmbedAudio.svg?style=social&label=Stars
[github watchers]: https://img.shields.io/github/watchers/jonnitto/Jonnitto.PrettyEmbedAudio.svg?style=social&label=Watch
[github followers]: https://img.shields.io/github/followers/jonnitto.svg?style=social&label=Follow
[follow jon on twitter]: https://img.shields.io/twitter/follow/jonnitto.svg?style=social&label=Follow
[twitter]: https://twitter.com/jonnitto
[fork]: https://github.com/jonnitto/Jonnitto.PrettyEmbedAudio/fork
[stargazers]: https://github.com/jonnitto/Jonnitto.PrettyEmbedAudio/stargazers
[subscription]: https://github.com/jonnitto/Jonnitto.PrettyEmbedAudio/subscription
[followers]: https://github.com/jonnitto/followers
[license]: LICENSE
[neos cms]: https://www.neos.io
[jonnitto.plyr]: https://github.com/jonnitto/Jonnitto.Plyr
[settings.jonnitto.yaml]: Configuration/Settings.Jonnitto.yaml
[`jonnitto.prettyembedaudio:component.audio`]: Resources/Private/Fusion/Component/Audio.fusion
[`jonnitto.prettyembedaudio:content.audio`]: Resources/Private/Fusion/Content/Audio.fusion
