# time_line_example
---
## css Properties Elements.

1) backdrop-filter:- it applies graphical Effects(like blur or color Adjustments) to the area behind a semi-transparant element. 

* mostly use to create frosted glass effect 
> if you are using background color then it's transparency Should be less then 50% then drop filter will work properly.

>> example :-
```
.element
{
    backdrop-filter:blur(10px);
}
``` 
we can use brightness, contrast,Grayscale,sepia,saturate,Hue Rotate or all filter at once.

```
backdrop-filter: blur(5px) brightness(120%) contrast(150%);

```

```
to show of hide any element in the webpage we can use following kwy points 

1) the object you want move make that thing Absolute so it can move easily.
2) if want to hide at right side provide it's vlaue in -ve , like right:-40%, -40px etc 
3) if want to hide something on the left side mark it's value as left:-10% etc

these will made element out of the viewpoint or screen.
```

### What is a Timeline in GSAP?

A **Timeline** in GSAP is a container that holds multiple animations and gives you fine control over their playback. It allows you to chain animations together, and it’s extremely useful when you want to create complex animations with precise timing.

### Common Playback Functions for GSAP Timelines

#### 1. **`.play()`**
The `play()` method is used to start or resume an animation timeline. If your timeline has been paused, calling `.play()` will resume the timeline from its current position. If the timeline is at the end, it will start from the beginning.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 }); // Move box to x = 300px
timeline.play(); // Starts the timeline
```

You can also use `.play()` with a specific position to start from a certain point in time or a labeled marker.

```javascript
timeline.play(1); // Start playing from 1 second into the timeline
```

#### 2. **`.pause()`**
The `pause()` method halts the timeline at its current position, essentially freezing it. This is useful when you want to stop the animation and resume later, either programmatically or based on user interaction.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 });
timeline.pause(); // Pauses the timeline
```

#### 3. **`.reverse()`**
If you want to play the timeline backward, you can use the `reverse()` method. This function plays the timeline in reverse, starting from the current position and going back to the start.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 });
timeline.reverse(); // Plays the animation backward
```

You can also specify a certain time to reverse from:
```javascript
timeline.reverse(1); // Reverses from 1 second into the timeline
```

#### 4. **`.seek()`**
The `seek()` method lets you jump to a specific point in the timeline, either by providing a time value (in seconds) or by referencing a label (if you've set one). This is helpful when you want to quickly skip to a specific frame or part of the animation.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 }).to(".box", { duration: 2, y: 200 });

// Jump to 1.5 seconds into the timeline
timeline.seek(1.5);

// Or jump to a label if you’ve defined one
timeline.addLabel("midway", 2);
timeline.seek("midway");
```

#### 5. **`.restart()`**
If you want to restart the timeline from the beginning, regardless of where it currently is, use the `restart()` method. This is useful for triggering animations again, even if they were paused or completed.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 });
timeline.restart(); // Restarts the timeline from the beginning
```

#### 6. **`.progress()`**
The `progress()` method allows you to get or set the current progress of the timeline. Progress is represented as a value between `0` (start) and `1` (end). You can also use it to control the timeline’s playback directly by passing a number between 0 and 1.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 });

// Get the current progress of the timeline
let currentProgress = timeline.progress();
console.log(currentProgress); // e.g., 0.5 if halfway through the animation

// Set the progress to 50%
timeline.progress(0.5); 
```

#### 7. **`.totalProgress()`**
`totalProgress()` works similarly to `progress()`, but it reflects the progress of the entire timeline, including any nested timelines. It's useful if your timeline contains other nested timelines, and you want to track the overall completion.

**Example:**
```javascript
let timeline = gsap.timeline();
let nestedTimeline = gsap.timeline();
nestedTimeline.to(".box", { duration: 2, x: 300 });

timeline.add(nestedTimeline);
console.log(timeline.totalProgress()); // Shows the total progress of both timelines
```

#### 8. **`.isActive()`**
The `isActive()` method checks whether the timeline is currently active—meaning it’s either playing or not paused. It returns `true` if the timeline is playing or paused but not completed, and `false` otherwise.

**Example:**
```javascript
let timeline = gsap.timeline();
timeline.to(".box", { duration: 2, x: 300 });

console.log(timeline.isActive()); // Returns true if the timeline is still active
```

### Combining Timeline Controls for Interactive Animations

One of the powerful features of GSAP timelines is how easily you can combine different playback controls for interactive animations. For example, you can trigger specific actions based on user events, like mouse clicks, hover, or scroll.

**Example: Interactive Animation Control**
```javascript
let timeline = gsap.timeline({ paused: true });

timeline.to(".box", { duration: 2, x: 300 });

document.querySelector(".start-button").addEventListener("click", () => {
    timeline.play();
});

document.querySelector(".pause-button").addEventListener("click", () => {
    timeline.pause();
});
```

### Conclusion

GSAP’s timeline features allow you to control your animations with great flexibility. Whether you're building interactive animations, creating complex sequences, or just want to have more control over when animations play, pause, or reverse, these timeline functions are essential tools to master. By combining them creatively, you can create animations that react to user interactions or sync up perfectly with other content.

Happy animating!