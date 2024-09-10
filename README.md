# CSS Animated Borders for OBS
These are the files for my tutorial on how to create animated borders for OBS.

## Installation
1. Add `animated_border.html` into OBS as a browser source.
2. To customize, go into the browser source properties, and create a `.border` selector.
2. The following properties of the `.border` selector are available for customization (see below for more details):
    - width
    - height
    - background: conic-gradient()
    - filter: blur()
    - animation-duration
    - border-radius (for round and round-ish sources)

## Customization
### Background
The source file uses a special variable called `--gradient-angle` which need to be set as the "from" variable of the conic-gradient background. Play around with the colors. You can use hexadecimals or the rgba() function if you want to have transparency (but don't combine them in a single conic-gradient declaration).
```css
.border {
    background: conic-gradient(
        from var(--gradient-angle),
        #0000ff, 
        #4b0082,
        #800080,
        #a020f0,
        #d8bfd8
    );
}
```

```css
.border {
    background: conic-gradient(
        from var(--gradient-angle),
        rgba(0, 0, 255, 1),
        rgba(75, 0, 130, 1),
        rgba(128, 0, 128, 1),
        rgba(160, 32, 240, 1),
        rgba(216, 191, 216, 1)
    );
}
```

### Blur Filter
To customize the spread or size of the blur, set the `filter: blur(30px)` to a size you prefer.
```css
.border {
    filter: blur(8px);
}
```

### Animation Duration
To change the speed of the animation, set the `animation-duration` property. You can use `s` for seconds and `ms` for milliseconds`.
```css
.border {
    animation-duration: 8s;
}
```

### Border Radius
If you have a source with rounded corners or a circular source, you can set the `border-radius` property. If you have a circular source (say, a camera), you should set this property to the same size as your width and height.
```css
.border {
    border-radius: 20px;
}
```