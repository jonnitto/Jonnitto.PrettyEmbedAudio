[![Latest stable version]][packagist] [![Total downloads]][packagist] [![License]][packagist] [![GitHub forks]][fork] [![GitHub stars]][stargazers] [![GitHub watchers]][subscription] [![GitHub followers]][followers] [![Follow Jon on Twitter]][twitter]

# Jonnitto.PrettyEmbedAudio

Prettier embeds for your Audio sources in [Neos CMS]

| Version | Neos   | Maintained |
| ------- | ------ | :--------: |
| 1.\*    | >= 5.3 |     ✗      |
| 2.\*    | >= 5.3 |     ✗      |
| 6.\*    | >= 7.3 |     ✓      |

> The version jump was made to have all packages from the PrettyEmbed series on the same number

## Installation

Most of the time you have to make small adjustments to a package (e.g. configuration in `Settings.yaml`). Because of
that, it is important to add the corresponding package to the composer from your theme package. Mostly this is the site
packages located under `Packages/Sites/`. To install it correctly go to your theme package (e.g.`Packages/Sites/Foo.Bar`)
and run following command:

```bash
composer require jonnitto/prettyembedaudio --no-update
```

The `--no-update` command prevent the automatic update of the dependencies. After the package was added to your theme
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
| Javascript API                     |                    |   ✓    |
| Filesize (JS & CSS)                |      smaller       | bigger |

All packages from the PrettyEmbed series have the benefit of a better frontend performance since the player gets only
loaded on request. So, no iframe/video get's loaded until the user wants to watch a video or listen to audio.

## Customization

### Global settings for the whole PrettyEmbed series

The settings will be set globally from the [PrettyEmbedHelper] package. These are the default settings for audio:

```yaml
Jonnitto:
  PrettyEmbed:
    # Set this to true for debug output
    debug: false

    # If you have your own AlpineJS in your setup, you can disable the check here. Alpine must be an global variable
    includeAlpineJsCheck: true

    # If you want to use your own assets, set this to false
    includeAssets:
      css: true
      js: true

    # Can be `lazy`, `eager` or `null`
    loadImageStrategy: lazy

    # If this is set to a string, the element gets wrapped with a div and the class with the giving string.
    # If set to true, the element gets wrapped with a div without any class.
    # If set to false, the element get not wrapped at all
    wrapper: false

    # The buttons which get injected (file content) to the player.
    # You can also overwrite the button Fusion components
    button:
      play: "resource://Jonnitto.PrettyEmbedHelper/Public/Assets/PlayButton.svg"
      pause: "resource://Jonnitto.PrettyEmbedHelper/Public/Assets/PauseButton.svg"

    # This is the maximum width of a custom preview image
    maximumWidth: 1920
  Audio:
    # If true, the browser will offer controls to allow the user to control
    # audio playback, including volume, seeking, and pause/resume playback.
    controls: true

    # If true, the browser will automatically seek back
    # to the start upon reaching the end of the audio.
    loop: false

    # This enumerated attribute is intended to provide a hint to the browser about what
    # the author thinks will lead to the best user experience with regards to what content
    # is loaded before the audio is played. It may have one of the following values:
    #  - none       Indicates that the audio should not be preloaded.
    #  - metadata   Indicates that the browser should load only metadata when the page loads
    #  - auto       Indicates that the whole audio file can be downloaded, even if the user is not expected to use it
    preload: metadata

    # https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio#attr-crossorigin
    # anonymous || use-credentials || true || false
    crossorigin: false
```

If no node property is giving, these default values will be taken. If you, for example, want to let the editor choose
if the audio should play in a loop you can activate the mixin like thos:

```yaml
"Jonnitto.PrettyEmbedAudio:Content.Audio":
  superTypes:
    "Jonnitto.PrettyEmbedHelper:Mixin.Loop": true
```

These are the available mixins:

| Mixin name                                | Description                         | Enabled |
| ----------------------------------------- | ----------------------------------- | :-----: |
| `Jonnitto.PrettyEmbedHelper:Mixin.Groups` | Enables the inspector groups        |    ✓    |
| `Jonnitto.PrettyEmbedHelper:Mixin.Loop`   | Loop the audio, defaults to `false` |         |

### Fusion

If you want to use the player as a pure component, you can use the `Jonnitto.PrettyEmbed:Presentation.Audio`
Fusion prototype.

If you want to read the node properties and let the package handle all for you, you should use the
[`Jonnitto.PrettyEmbedAudio:Content.Audio`] prototype. For easier including in your own node types, you can disable
the content element wrapping with `contentElement = false`. This is useful if you want to create for example a text
with audio node type.

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
[`jonnitto.prettyembedaudio:content.audio`]: Resources/Private/Fusion/Content.Audio.fusion
