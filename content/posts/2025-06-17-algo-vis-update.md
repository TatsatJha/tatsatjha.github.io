+++
title = "Alog-Vis Update"
date = "2025-06-17"
+++

All right, big update on Algo vis. I was very unhappy with how a lot of the state and the information as being stored when I started up this project so I decided to go back throuhg and try to rethik of the way all of the information is sotred and passsed around. I eventually was able to find a way to rpetty cleanly seperate out the state of the graph by putting it much higher up in the component tree and I have just a handful of functions that updates the render.

Currently, the rendering is a little janky. I went with my usual sort of
instinct on it by rendering the lines and points using divs and then using some
math to position them properly with css. I have a feeling there has to be a
better solution though so I'm planning on going through that and cleaning it up
in a similar way as I did with the state and doing some research on how to
better draw lines and points with javscript specifically.

lso in my inital vision for htis project I had drawn it up and wrote out the
basic website so that it would render a grid and the algorithms we would be
visualizing would be exclusively using a grid. That's the biggest change I've
made recently which is that I'm now allowing any sort of graph to be made by the
user and visualized.

After the project is done I'm hoping we have a maintable and extensible enough
architecture that we can use it for other things as well such as building trees
and the like. I feel like once I have the framework built out for rendering
these structures and for visualizign the algorithms step by step it shoudl be a
pretty straight forward process of extending it by literally just learning and
writing out new algoirthms.

But yeah, at this point I'm looking for a better way to render stuff but I'm
happy with where we are at in terms of storing the state of the graph.


