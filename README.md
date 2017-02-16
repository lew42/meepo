![DotA - Meepo](/meepo.png?raw=true "DotA - Meepo")

<a href="http://zohoth.deviantart.com/art/Crystal-Scavenger-Meepo-Render-560975279">Crystal Scavenger Meepo Render</a> by <span class="username-with-symbol u"><a class="u regular username" href="http://zohoth.deviantart.com/">Zohoth</a><span class="user-symbol regular" data-quicktip-text="" data-show-tooltip="" data-gruser-type="regular"></span></span> on <a href="http://www.deviantart.com">DeviantArt</a>

# Stop using relative requires

```javascript
require("../../whatever");  // no good
require("whatever"); // mmm, better
```

How?  It's really easy.  Here's the gist:

### Create a secondary `node_modules` folder

Notice this repo has `/node_modules/` and `/code/node_modules/`.

- Root `/node_modules/` works as usual.  `npm install` your external packages here.
- `/code/node_modules/` is reserved for "local" packages.
- Any file within `/code/` can `require()` any of these "local" packages, without a relative path.
- Check the `.gitignore` to see how to ignore the root `/node_modules/` and not ignore the `/code/node_modules/`

### The submodule problem

If you want multiple, reusable components, you might consider publishing several `npm` modules.  But, if they're tightly coupled (they all depend heavily on each other), then you ..

[Lerna](https://github.com/lerna/lerna) is one.  Lerna has a bunch of options to `npm publish`, and manage the version numbers.  I'm not quite there yet.

Also, I saw something about using path/environment variables, but not sure how that works.  Please use the issues if you're aware of other solutions to this problem.


### About the name, Meepo

Others have been calling them "monorepos", which I believe is short for monolithic.  Meepo is a hero from the DotA video game, and is characterized by the ability to create copies of himself.
