# Audio player theme component for Hugo websites

This [theme component](https://gohugo.io/hugo-modules/theme-components/#readout) for [Hugo Static Sites](https://gohugo.io/) allows you to embed audio players based on [jplayer](https://jplayer.org/). One of the advantages of this approach over normal html5 web audio players is that it allows more finetuned customization and tweaks.

You can see it in action on [madskjeldgaard.dk](https://madskjeldgaard.dk) and [exformal.art](https://exformal.art)

## Installation

Put this folder in your themes folder in your hugo website. You can use git submodules to do this:

```bash
git submodule add git@github.com:madskjeldgaard/hugo-audio.git themes/hugo-audio
```

Then add it your list of themes:

Note: It has to be the last component, after your main theme.

```toml
theme  = [ "exformal-hugo-theme", "hugo-audio"]
```  

The theme component **expects you to have jquery installed**.

## Configuration

## Usage

### Shortcodes

#### Simple Audio Player

Embeds a simple audio player in your content. You can call this in your markdown files like this, given that the audio is in the folder `static/audio/music`:
 
```
{{< simpleaudioplayer title="15:15 PM (excerpt)" url="/audio/music/04 - Mads Kjeldgaard - 15_15 PM (Excerpt) (EX001).mp3" >}}
```

The player includes some default settings that may be overwritten like this:

```
{{< simpleaudioplayer title="15:15 PM (excerpt)" url="/audio/music/04 - Mads Kjeldgaard - 15_15 PM (Excerpt) (EX001).mp3" showTitle=false showDuration=true showProgressBar=false >}}
```

### Partials

#### Simple Audio Player

![readme-assets/simple-audio-player.png](readme-assets/simple-audio-player.png) 

This embeds a simple audio player that plays an audio file with the given path.

Usage in a hugo template:

```hugohtml 
{{ partial "simple-audio-player.html" (dict "path" "/audio/music/threebursts.mp3" "title" "Three bursts of Noise") }}
```
### Customization

You can style the players by overwriting the default css like this:
```css
.jp-play.hugo-jp-play {
  background-color: var(--background-color) !important;
  color: var(--text-color) !important;
}

.jp-controls.hugo-jp-controls {
  font-family: Helvetica, sans-serif !important;
  color: var(--text-color) !important;
}

.jp-title.hugo-jp-title {
  color: var(--text-color) !important;
}

.jp-duration.hugo-jp-duration {
  color: var(--text-color) !important;
}

.jp-progress.hugo-jp-progress {
  background: var(--background-color) !important;
}

.jp-play-bar.hugo-jp-play-bar {
  background: var(--primary-color) !important;
}
```
