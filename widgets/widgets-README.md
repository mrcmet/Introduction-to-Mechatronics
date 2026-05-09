# Widgets — Introduction to Mechatronics

Interactive HTML widgets hosted on GitHub Pages and embedded in the course Obsidian Publish site.

**Gallery**: https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/

## Structure

```
widgets/
├── index.html              ← live widget gallery
├── dynamics/               ← work-energy, impulse-momentum, etc.
├── kinematics/             ← rigid body motion, velocity/acceleration diagrams
├── controls/               ← PID tuners, block diagrams, step response
├── sensors-actuators/      ← motor curves, sensor range visualizers
├── circuits/               ← op-amp, RC circuits, signal conditioning
└── programming/            ← flowcharts, state machines, timing diagrams
```

## Adding a new widget

1. Claude generates the `.html` file
2. Save it to the correct subject folder: `widgets/<subject>/<name>.html`
3. Add a card entry to `widgets/index.html` in the matching section
4. Push:
   ```bash
   git add widgets/
   git commit -m "add <name> widget"
   git push
   ```
5. Live in ~30 seconds at `https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/<subject>/<name>.html`

## Embedding in Obsidian

Paste this into any `.md` note (adjust path and height):

```html
<iframe
  src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/<subject>/<name>.html"
  width="100%"
  height="450"
  style="border: none; border-radius: 8px;"
  loading="lazy"
  title="Widget description">
</iframe>
```
