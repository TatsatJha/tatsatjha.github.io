+++
title = "Summer 2025 Review"
date = "2025-08-10"
+++

It's been a long summer and I've been up to quite a bit of projects lately.
Here's a comprehensive overview of what I've been up to.

## Vantage Fit

Vantage Fit is an AI-powered fitness app I’ve been developing since last summer, with most of the progress made in the past couple of months. Since the start of summer, the app has undergone a full UI overhaul and a complete backend integration with Firebase, bringing a far more robust authentication/authorization system as well as full CRUD functionality for the program builder and trainer features.

The AI integrations are also moving forward. A basic RAG system is in development, the document corpus is being expanded, and the exact integration points are being carefully planned.

I’d like to share code snippets here, but the codebase is spread across so many files that it’s difficult to choose just one. That said, here’s a section I’m particularly proud of.

```html
    <>
      <div className='absolute w-screen top-36'>
        <ProgramName name={name} setName={setName}></ProgramName>
        <Sessions sessions={sessions} setSessions={setSessions}></Sessions>
      </div>

      <div className='flex justify-end bg-white shadow-inner w-full'>
      
        <div className="fixed bottom-0 right-10 flex gap-4 p-4">
          <button
            onClick={addSession}
            className="bg-gray-600 text-white px-6 py-2 rounded-lg shadow-md hover:bg-gray-700 focus:ring-2 focus:ring-blue-300 transition-all"
          >
            Add Session
          </button>
          <Link to={"../my-programs"}>
            <button 
            className="bg-gray-600 text-white px-6 py-2 rounded-lg shadow-md hover:bg-gray-700 transition-all"
            >
              Cancel
            </button>
          </Link>
          <Link to={"../my-programs"}>
            <button
              onClick={save}
              className="bg-blue-600 text-white px-6 py-2 rounded-lg shadow-md hover:bg-blue-700 transition-all" 
            >
              Save
            </button>
          </Link>
        </div>
      </div>
    </>
```

The above is the entire component for the program builder fit with all of the
buttons, components, React hooks that make it function. It was what saw the
majority the UI overhaul this summer and ended up being something I was quite
happy with in terms of code quality.

## Algo Vis

I built Algo Vis to explore and visualize algorithms, starting with pathfinding techniques like Dijkstra’s and A*. The project’s goal was to make algorithm behavior intuitive and engaging through interactive visualizations.

Right now, Algo Vis visualizes Dijkstra’s algorithm with a responsive, extensible setup. My plan is to expand it with additional pathfinding algorithms and eventually include visualizations for data structures like binary trees and red-black trees—plus animations for the algorithms that operate on them.

For example, here’s the core canvas component in the app:
``` html
    <canvas
      ref={canvasRef}
      className="mt-16"
      width="1000"
      height="1000"
      onMouseDown={handleMouseDown}
      onMouseMove={handleMouseMove}
      onMouseUp={handleMouseUp}
      onMouseOver={handleMouseOver}
      onMouseLeave={handleMouseLeave}
    />
```


I love how clean this rendering logic is. Just simple dimensions, light styling, and intuitive event handlers for user interaction.

Behind the scenes, the application logic follows an object-oriented structure that integrates with React’s useState hook. While classes and objects aren’t as common in modern JavaScript, I found this approach made the architecture clear and maintainable for this project.

The project is mostly complete for its current scope. I’ll be publishing a live demo on here soon, and will update it whenever I add new features like tree algorithm visualizations.

## Jarvis

The Jarvis project is a personal project of mine that was actually inspired by
a time I went to the Apple store, looked at the home pods and figured that I
could just turn my laptop (and really any combination of a server, microphone
and speakers) into a smart speaker.

Thus, after tinkering for a few weeks, I had integrated a handful of models
into a python script along with some software in lower level languages to reduce 
latency.

The result was Jarvis: a voice-powered smart speaker that runs entirely offline and only listens when prompted.

Jarvis already delivers on my original vision, but I’m far from done. I see enormous homelab potential and am working on expanding his command set, improving his voice output, and integrating an open source LLM so he can answer general questions more intelligently. He currently has text-to-speech capabilities, but I’m aiming for a lower latency, more natural solution.

For now, I’m thrilled with his progress. Building Jarvis has been incredibly fun, and the possibilities for making him more powerful—and eventually integrating him into my personal systems—are wide open.

## Hugo Bibliography

Hugo Bibliography is a open source project I wrote while working for DH-Tech.
You can find the full project here: https://github.com/dh-tech/hugo-bibliography

It is essentially a plugin for the Hugo static site generator that allows you to
render and share bibliographic citations from Zotero, directly into your hugo
website.

It basically works using a very complex bibliography shortcode which I will
include part of here to demonstrate how unique and sometimes infuriating Hugo templates can be.

```html
<ul style="list-style-type: none;" class="apa-citation-list">
    {{- range $citation := $sortedCitations }}
        {{- $collections := $citation.citation.collections | default (slice) }}
        {{- if eq (len $collections) 0 }}
            {{- partial "render-citation.html" . }}
        {{- end }}
    {{- end }} 

    {{- range $collections }}
        {{ partial "render-collection.html" (dict "collection" . "citations" $sortedCitations) }}
    {{- end }}
</ul>
```

As you can see we're essentially rendering citations that have been sorted into several sub collections using the range and if statements in hugo templating. Later we also encode this output with CoinS data and there is a lot more involved in terms of extracting, formulating, and sorting these citations for rendering.

I won't go into too much more detail here but if you'd like to read more about hugo-bibliography, check out the article
I wrote on it for the [DH-Tech website](https://dh-tech.github.io/blog/2025/07/11/hugo-bibliography/)

## Neovim

For those of you who don't know, Neovim is a fully-customizable text editor that
uses Lua as its scripting language. It's a fork of vim which I'm sure you're
familiar with if you've ever dug around with the terminal.

This summer saw me transitioning from using vscode to neovim exclusively. It took some time
to get used to the new development environment and I almost gave up on it, but I
can say that I'm never going back.

Setting up my own neovim configuration using kickstart was one of the most
enjoyable parts of my development journey this summer. I have a much better
understanding of how a development environment works and some of the key features
that go into it.

I'm confident that I would have never looked into how LSPs, fuzzy finders,
package managers, and other tools work if I had stuck with something like vscode.

Not to mention, setting up a configuration in hindsight was pretty easy to do
because of the kickstart project. It set me up with Telescope, Treesitter, lazy,
and other basic tools out of the box that made it super easy to extend my
configuration. 

For example, adding an LSP server for a new language is incredibly easy. The
following line was all I had to do to get a basic LSP server for typescript
working in my neovim setup.

```lua
ts_ls = {}
```

To add the oil neovim plugin, (which I am loving by the way, so much easier to interact with the file system)
I just had to add the following lines to my config.

```lua
  {
    'stevearc/oil.nvim',
    ---@module 'oil'
    ---@type oil.SetupOpts
    opts = {},
    dependencies = { { 'echasnovski/mini.icons', opts = {} } },
    lazy = false,
  },
  -
```

This is all to say the process of setting up and using neovim was actually rather straight forward and incredibly worth while.
It has made developing and writing code something I make excuses for and you
just have a lot of pride in setting up your own development environment.

So ten out of ten, I would recommend giving neovim a try to every developer out there.



## Deep Learning

Just to wrap this up, I have been taking some deep learning courses lately. Not too much to report
right now in terms of projects I've written with these new skills but hopefully in the next major update I will be
talking about my own model I'm wanting to build.


## Next Steps

Here are the next steps for each of the projects I am still working on for the
upcoming Fall.

- Extend out Algo-Vis with some more algorithms and perhaps integrate Tree structures into the site. This is a rather complete project so we'll see how much more I work on it

- Build out and hopefully beta test Vantage Fit with full AI integrations and perhaps even a custom model for progression recommendations.

- Give Jarvis some more features I have tons of ideas including building a
custom media player for him, having him sync into certain spreadsheets I have,
have him help me track nutrition, to-do lists and I even want to build a custom facial
detection model for him.

But yeah that wraps up the summer development update. 

Thank you for reading!
