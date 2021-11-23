# Approaches to making (reusable) charts with Svelte and D3.js

Some work-in-progress notes on making reusable charts.

This will assume some knowledge of Svelte and D3.js.

## Introduction

Making charts using Svelte and D3.js is relatively easy and (some might argue) more fun than doing the same with just D3.

This is not a slight on D3 which remains amazing. But D3 has a pretty steep learning curve and can be tricky to work with in some cases, such as when charts need to be resized to fit a new window size, or new data is loaded. D3 can and does do all of this but Svelte can simplify a lot of this for us. In particular, Svelte cna handle things like resizing with very little effort and switching between datasets with transitions are exptremely simple in most cases with Svelte.

## Shaking things up

One of the reasons that D3 often seems difficult to learn is that traditionally D3 was seen as mostly monolithic: Charts were built entirely in D3 and relied on that to function. And charts were built very imperatively: we would specify exactly how and where we wanted each part of the chart, from the axes, to the bars or lines and the annotations. This could often become overwhelming.

Fortunatley there is another way. Around D3 version 4 (Check) D3 was converted to and released as a set of modules. Essentially all of the individual parts of D3 were made available as self-standing helpers. This meant developers could pick and choose the pieces they wanted to use rather than use the entire library. Obviously developers could always just use the pieces of D3 they wanted but were still required to load the entire library before D3 version 4.

Now developers could pick and choose and easily combine with other tools, like Svelte.

The benefit of this this may not be immediately obvious but as we'll see, being able to just use the parts of D3 you need, without having to use the entire D3 library is powerful and liberating.

In the following examples, we'll look at how we can do exactly that by usig just the bits of D3 that are necessary and offset as much of the work to Svelte as possible.

## The idea behind Svelte and D3

The main idea behind combining Svelte and D3 is to use the best parts of each D3 and Svelte. We pick the pick the bits D3 dos best, like scales, SVG lines and areas, and using Svelte to add the other bits like reactivy and animations.

## The main areas

#### Managing data (Svelte & D3)

Svelte has a number of built-in functions for managing data which make handling data across charts or even pages almost trivial.

#### Handling resizes (Svelte)

Svelte also handles things like page resizes and changing data with ease. And because Svelte makes it easy to mix HTML, SVG, CSS and Javascript, we can use any of these to draw the elements of charts and not be bound to doing everything as an SVG.

#### Components(Svelte)

One last thing: Svelte is component-based which makes it a lot simpler to break charts down into reusable parts, for example: and axis component, or a line generator component. Almost anything can be split out into a component.

#### Scale (D3)

On the other hand, D3 has its own superpowers. One of those is without doubt scales, for mapping values to your available space.

#### SVG shapes (D3)

D3 also includes an amazing array of shape generators that make creating anything from a simple line to a polygon easy. D3 also includes a long list of tools for doing essential data manipulation which you'll need in data visualization.
