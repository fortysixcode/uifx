### Audio library designed for UI sound effects (UIfx)

Demo: https://wle8300.github.io/uifx-demo/

## Usage

```
npm install --save uifx
```

```
import UIfx from 'uifx'
import bellAudio from './my-sounds/bell.mp3'

const bell = new UIfx(
  bellAudio,
  {
    volume: 0.4, // number between 0.0 ~ 1.0
    throttleMs: 100
  }
)

// playback
bell.play()

// temporarily change volume
bell.play(0.25) // will play at 0.25 volume
bell.play() // reverts back to 0.4 volume

// set volume
bell.setVolume(0.5)
bell.play()

// ...chainable
bell.setVolume(0.5).play()
```


## Technical

It uses the [`HTMLAudioElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement) API under-the-hood so it's stable across all major desktop/mobile browsers. It also preloads audio files so sounds are immediately ready for playback.

Even though it can preload audio, it's a good idea to package your audio files locally since you don't want to rely on a 3rd-party to host your audio files.

The library doesn't have any dependencies.


## Why use UIfx?
 
It's designed specifically for soundfx so it preloads audio files to ensure it's immediately playable, and will spawns an audio player for each playback. This makes it lightweight and performant when compared to fully-fledged libraries like SoundManager or Howler.


