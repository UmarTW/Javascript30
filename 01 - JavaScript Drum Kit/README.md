## Javascript Drum Kit
Script listens for keydown event with keycodes corresponding to the ones displayed on screen. On match, audio is played and key transforms. 

![](images/screenshot.png)

click <a href="">here<a/> for demo.

### Process 
`document.querySelector` is used to bind the pressed key with it's corresponding `<audio>` element, and it's `<div>` using their assigned `data-key` attribute.

When a keycode is matched, it's attached audio is played,and a class .playing is added to it for the transform.
```
function playSound(e) {
  const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
  const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);

  if(!audio) return; // stop the function from running entirely
  audio.currentTime = 0; // rewind to the beginning
  audio.play();
  key.classList.add('playing');
 }
```
To remove the .playing class another function `removeTransition()` is used to listen for transform property

```
function removeTransition(e){
  if(e.propertyName !== 'transform') return // skip it if it's not a transform
  this.classList.remove('playing');
 }
```
This about me page is only as good as my comprehension of this code. I am aware of how amateurish it may seem and promise to flesh it out properly as soon as I can. In the meantime, thank you! 
