
https://github.com/kittykatattack/learningPixi guide with 5.3.10
https://github.com/ForkandBeard/Alferd-Spritesheet-Unpacker/releases Desktop Sprite Splite & Detection tool
https://www.leshylabs.com/apps/sstool/ Online free Sprite Detection tool
https://free-tex-packer.com/app/ Online free texture packer
https://pixijs.io/examples/#/sprite/texture-swap.js texture Swap guide

In Pixi.js, you can check for the release of multiple buttons simultaneously by using event listeners for each button and setting a flag for each button that is pressed. In your event listener function, you can check the state of each flag and take appropriate action when all four buttons have been released.

Here's an example of how you might implement this:
-
```javascript
let rightButtonPressed = false;
let leftButtonPressed = false;
let upButtonPressed = false;
let downButtonPressed = false;

// Event listener for right button release
rightButton.addEventListener('pointerup', () => {
    rightButtonPressed = false;
    checkAllButtonsReleased();
});

// Event listener for left button release
leftButton.addEventListener('pointerup', () => {
    leftButtonPressed = false;
    checkAllButtonsReleased();
});

// Event listener for up button release
upButton.addEventListener('pointerup', () => {
    upButtonPressed = false;
    checkAllButtonsReleased();
});

// Event listener for down button release
downButton.addEventListener('pointerup', () => {
    downButtonPressed = false;
    checkAllButtonsReleased();
});

function checkAllButtonsReleased() {
    if (!rightButtonPressed && !leftButtonPressed && !upButtonPressed && !downButtonPressed) {
        // All buttons have been released
        console.log("All buttons have been released!");
    }
}


document.addEventListener("keydown", function(event) {
  if(event.keyCode === 37) {
    leftButtonPressed = true;
  }
  if(event.keyCode === 38) {
    upButtonPressed = true;
  }
  if(event.keyCode === 39) {
    rightButtonPressed = true;
  }
  if(event.keyCode === 40) {
    downButtonPressed = true;
  }
});

document.addEventListener("keyup", function(event) {
  if(event.keyCode === 37) {
    leftButtonPressed = false;
    checkAllButtonsReleased();
  }
  if(event.keyCode === 38) {
    upButtonPressed = false;
    checkAllButtonsReleased();
  }
  if(event.keyCode === 39) {
    rightButtonPressed = false;
    checkAllButtonsReleased();
  }
  if(event.keyCode === 40) {
    downButtonPressed = false;
    checkAllButtonsReleased();
  }
});
```