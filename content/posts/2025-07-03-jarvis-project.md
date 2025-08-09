+++
title = "Jarvis Project"
date = "2025-07-03"
+++

Okay story time. So basically I was at the mall the other day and we went by the
apple store right and I had the thought come to me of like. "Man thosse home pods,
they look really cool. They feel really cool but golly it just sucks that apple
definitely is spying on you with them." Not only that but because they tend to
be connected to the internet, I don't want it to be able to do much cuase then I
would opening up security vulnerabilities and potentially leaking my own data.

So basically I think "You know what, a smart speaker is just a microphone, a
speaker, and a small computer to do some procressing and then of course most of
them are connected to the internet so that they can do most of the complicated
and intensive processing in the cloud but I have everything I would need to turn
my laptop intoa  smart speark."

So I did, I began just yesterday, I looked into how to record my voice and then
take that speech and turn it into text using an open source model. I decided to
use Whisper. From there I figured out how to play sounds and set up a text to
speech bot and I've written out all the functions to where I acutally have a
pretty darn extensible system.

At this point I can turn on Jarvis and ask him to play pretty much any song and
he'll be able to. I can also do a few other commands but truth be told once I
hook Jarvis up to a proper LLM I can just ask him things and he'll be able to
respond simiarily to if I was talking to something like ChatGPT.

The main benefit is of course that all the procesing and computing happens
locally. He does not need wifi except for very specific commands where he's
asked to download something. 

The drawback right now though is just latency and I'm working on finding ways
around that and mitigating the latency as much as possible. Right now I have all
of the models running on my laptop's cpu. If I gave Jarvis a proper GPU to run
on he'd be a lot more capable I'm sure, but I'm quite happy with having turned
my laptop into a smart speaker essentially. 

I plan on extending Jarvis out some more, getting his text to speech to resemble
Jarvis from the movies more and then of course lowering that latency, giving him
more commands and potentially integrating him into my workflows.
