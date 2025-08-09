+++
title = "algo-vis: Complete"
date = "2025-07-20"
+++

Update on the algo-vis project! It's basically done. I've been waiting to write
this update for a while but we made some pretty large changes to the project.
Last time I was really not happy with the rendering system we had rolled up. It
was janky and messy and not very responsive and hard to maintain and extend.

Recently I learned how to use the canvas html element and update the dots and
lines on the canvas in response to changing state. The result was a much easier
to use, much better looking and much more responsive system.

We are now able to render a graph and move around the points and lines and
everything is responsive and smooth. In addition, I'm able to render the
shortest path between two points using Dijkstra's algorithm. I still need to
slow down the visualization a bit more but we have a really great framework now
for displaying graphs and paths.

I'm going to work on some other projects for a week or so and then come back to
this one. I'll slow down the visualizationa and add some more algorithms and
potentailly a tree mode.
