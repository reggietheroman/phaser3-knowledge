# Phaser3 Knowledge 

This repository contains simple explanations on how to do things using Phaser 3. It is not meant to be a definitive guide but a collection of my notes.

## Animations

**loading a spritesheet**

```
function preload() {
...
  this.load.spritesheet(
    'spriteKey',
    'assetUrl',
    {
      frameWidth: width,
      frameHeight: height,
      endFrame: lastFrame
    }
  );
...
}
```

where:
* spriteKey: [string  the key (or name) you will use to refer to the object in the rest of the code.
* assetUrl: [string] the url of the spritesheet. This is usually located in your assets folder. Used the same way images are added in html.
* width: [int] the width if each frame in the spritesheet.
* height: [int] the height of each frame in the spritesheet.
* lastFrame: [int] the number of the last frame. If your spritesheet has 10 frames, this will be 10.

**creating an animation**

```
function create() {
...
  var frames = this.anims.generateFrameNumbers(
    spriteName,
    {
      start: startingFrame,
      end: endingFrame,
      first: firstFrame
    }
  );

  var config = {
    key: key,
    frames: frames,
    frameRate: frameRate
  }

  this.anims.create(config);

  var explosion = this.add.sprite(x, y, spriteName);

  explosion.anims.play(key);
...
}
```
