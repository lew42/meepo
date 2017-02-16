![DotA - Meepo](/meepo.png?raw=true "DotA - Meepo")

<a href="http://zohoth.deviantart.com/art/Crystal-Scavenger-Meepo-Render-560975279">Crystal Scavenger Meepo Render</a> by <span class="username-with-symbol u"><a class="u regular username" href="http://zohoth.deviantart.com/">Zohoth</a><span class="user-symbol regular" data-quicktip-text="" data-show-tooltip="" data-gruser-type="regular"></span></span> on <a href="http://www.deviantart.com">DeviantArt</a>

# The simplest way to version control your sub modules

```
require("../../whatever");  // no good
require("whatever"); // mmm, better
```

### How?  Just create another `node_modules` within a sub folder

- Root `/node_modules/` works as usual.  `npm install` your external packages here.
- `/code/node_modules/` is reserved for "local" packages.
- Any file within `/code/` can `require()` any of these "local" packages, without a relative path.
- Check the `.gitignore` to see how to ignore the root `/node_modules/`, but check in the `/code/node_modules/`

### Other solutions

Lerna is one.  I saw something about using path/environment variables, but not sure how that works.


### About the name, Meepo

Others have been calling them "monorepos", which I believe is short for monolithic.  Meepo is a hero from the DotA video game, and is characterized by the ability to create copies of himself.
