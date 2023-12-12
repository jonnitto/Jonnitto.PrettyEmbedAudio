[![Latest stable version]][packagist] [![Total downloads]][packagist] [![License]][packagist] [![GitHub forks]][fork] [![GitHub stars]][stargazers] [![GitHub watchers]][subscription] [![GitHub followers]][followers] [![Follow Jon on Twitter]][twitter]

# Jonnitto.PrettyEmbedAudio

**For a detail guide, please visit the [PrettyEmbed Wiki](https://github.com/jonnitto/Jonnitto.PrettyEmbedHelper/wiki)**

Prettier embeds for your Audio sources in [Neos CMS]

| Version | Neos   | Maintained |
| ------- | ------ | :--------: |
| 1.\*    | >= 5.3 |     ✗      |
| 2.\*    | >= 5.3 |     ✗      |
| 6.\*    | >= 7.3 |     ✓      |

> The version jump was made to have all packages from the PrettyEmbed series on the same number

## Installation

Most of the time, you have to make small adjustments to a package (e.g., configuration in `Settings.yaml`). Because of
that, it is essential to add the corresponding package to the composer from your theme package. Navigate to this package
in your CLI and run the following command:

```bash
composer require jonnitto/prettyembedaudio --no-update
```

The `--no-update` command prevent the automatic update of the dependencies. After the package was added to your package
`composer.json`, go back to the root of the Neos installation and run `composer update`. Et voilà! Your desired package
is now installed correctly.

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
| Javascript API                     |         ✓          |   ✓    |
| Filesize (JS & CSS)                |      smaller       | bigger |

All packages from the PrettyEmbed series have the benefit of a better frontend performance since the player gets only
loaded on request. So, no iframe/video get's loaded until the user wants to watch a video or listen to audio.

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
[neos cms]: https://www.neos.io
[jonnitto.plyr]: https://github.com/jonnitto/Jonnitto.Plyr
