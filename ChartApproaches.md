# Approaches to making (reusable) charts with Svelte and D3.js

Some work-in-progress notes on making reusable charts.

This will assume some knowledge of Svelte and D3.js.

## Introduction

Making charts using Svelte and D3.js is relatively easy and (some might argue) more fun than doing the same with just D3.

This is not a slight on D3 which remains amazing. But D3 has a pretty steep learning curve and can be trucky to work with, especially when resizing charts for different views, or reloading data. In these cases there is often a lot of code required to achieve the end goal.

Combining Svelte and D2 shakes things up quite a bit, but it's worth taking the time to understand how the two can work together, and how they can make reusable chart elements easier to achieve.

## D3 as modules

Around D3 version 4 (Check) D3 was released as a set of modules. The benefit of this this may not be immediately obvious but as we'll see, being able to just use the parts of D3 you need, without having to use the entire D3 library is powerful and liberating.

In the following examples, we'll look at how we can do exactly that by usig just the bits of D3 that are necessary and offset as much of the work to Svelte as possible.
