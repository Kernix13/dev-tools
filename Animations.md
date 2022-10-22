# Analyzing the performance of your CSS Animations

Right now I only have notes from a WebDevSimplified video but more notes will be coming.

## How To Create Performant CSS Animations by Web Dev Simplified

- Go to `Perfoance` tab > `Throttling` > choose `6x` to see the result on less powerful computers
- Click `Record` button and stop after 2-3 seconds > drag out a small section of the bar graph at top to focus on it > open the main tab graph lower down:
  - 1. Layout, 2) Update, 3) Paint, 4) Composite Layers
- Layout and Painting takes a lot of time for the browser to do that – also look at the Summary section to see a pie chart of all the computation time -
- To dive in deeper go to triple dots > More tools > Rendering – look at `Paint Flashing` and `Layout Shift Regions` -
  - `Paint Flashing` – every time you do a repaint the browser will flash green -
  - `Layout Shifts` – you get a blue color for layout shifts -
- Go to triple dots > More Tools > `Performance Monitor` – can see the CPU usage and layouts/sec – make sure your cpu usage is low, not close to 100%
- And the layout/sec shows you the frames per second you are getting -

> Only do animations of transitions of 1. `opacity`, 2. `transforms` (translate, scale, rotate of other transform properties), and 3. `color` sparingly just for buttons and links
