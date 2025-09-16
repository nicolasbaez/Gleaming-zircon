# Gleaming-zircon
let's color

![buh](https://github.com/nicolasbaez/Gleaming-zircon/blob/main/xp054.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  colorMode(HSB, 2 * PI);
  clear();
  for (i = 0; i <= 2 * PI; i += PI / 2000) {
    stroke(i, 2 * PI, 2 * PI);
    strokeWeight(noise(i, k) * 4);
    r = noise(i * 0.01, k * 0.01, random(tan(i / noise(k * 0.5)))) * w * 0.5;
    point(r * cos(i + k) + w / 2, r * sin(i + k) + w / 2);
  }
  if (k == 0) saveGif("xp054.gif", 628, { delay: 0, units: "frames" });
  k += 0.01;
};
