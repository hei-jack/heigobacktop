# Select Mode

HeiGoBackTop has built-in four modes: `0 jump to the top, 1 jump to the bottom, 2 slow to the top, and 3 slow to the bottom`, which is convenient for users to choose according to the needs of the website.

## Jump to the top

The default mode is to jump to the top, and the user clicks the button to return directly to the top.

```javascript
let example = new HeiGoBackTop(0);

//or

example.onBeforeCreate(function(){
    this.mode = 0;
});
```

## jump to the bottom

After the user clicks the button, it jumps directly to the bottom of the page.

Just change `0` in the above method to `1`.

## Slow to the top

After the user clicks, it will slowly slide to the top according to the set speed and sliding distance.

```javascript
let example = new HeiGoBackTop(2); //The default sliding speed is 100px distance every 500 milliseconds

example.onBeforeCreate(function(){
    this.speed = 1000; //Change the sliding speed to 1 second
    this.distance = 300px; //Change the distance of each sliding to 300px
});
```

## Slowly to the bottom

After the user clicks, it will slowly slide to the bottom of the page according to the set speed and sliding distance.

Just change the example of slow sliding to the top `2` to `3`.