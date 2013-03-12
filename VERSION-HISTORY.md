
# Spritely version history

## Version 0.6.1
* Added some refinements from Gary hussey (http://bossninja.com/). Thanks Gary.
  spritely now correctly clears timeouts/intervals when destroying sprites.
* Added a goToFrame() method so you can set the current frame at any point.
* Fixed the .spStop method where the 'last FPS' value was not being set, and the user specified FPS being ignore when .spStart was called.

## Version 0.6
* Added events to the .sprite() method: on_first_frame, on_last_frame, on_frame
* Added start_at_frame: $('#sprite').sprite({fps: 9, no_of_frames: 24, start_at_frame: 8});

## Version 0.5
* Added a 'destroy()' method which will stop the element's sprite behaviour, without actually removing the element. Example: $('#my_sprite').destroy()

## Version 0.4
* Add up/down for 'pan' method. <ricky.hewitt@artlogic.net>
* Added 'dir' option for Sprites. This means a Sprite can be played in reverse.
* Removed alert message regarding jQuery.draggable (now uses console.log, if available) <ricky.hewitt@artlogic.net>

## Version 0.3b
* Added lockTo method for locking sprites to background images. $('#sprite').lockTo('#background, {'left': 380, 'top': -60, 'bg_img_width': 1110});

## Version 0.2.1
* Animate function will stop cycling after play_frames has completed

## Version 0.2 beta
* Added isDraggable method (requires jquery-ui) $('#sprite').sprite().isDraggable({start: null, stop: function() {alert('Ouch! You dropped me!')});
* Sprites may be set to play a limited number of frames when instantiated, e.g. $('#sprite').sprite({fps: 9, no_of_frames: 3, play_frames: 30})
* Sprite speed may be controlled at any point by setting the frames-per-second $('#sprite').fps(20);
* Sprites with multiple rows of frames may have there 'state' changed, e.g. to make the second row of frames
  active, use: $('#sprite').spState(2); - to return to the first row, use $('#sprite').spState(1);
* Background element speed may be controlled at any point with .spSpeed(), e.g. $('#bg1').spSpeed(10)
* Background elements may be set to a depth where 100 is the viewer (up close) and 0 is the horizon, e.g.:
  $('#bg1').pan({fps: 30, speed: 2, dir: 'left', depth: 30});
  $('#bg2').pan({fps: 30, speed: 3, dir: 'left', depth: 70});
* Relative speed of backgrounds may now be set in a single action with $('#bg1, #bg2').spRelSpeed(20);
  which will make elements closer to the horizon (lower depths) move slower than closer elements (higher depths)