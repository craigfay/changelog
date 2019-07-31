# About
This is a place I've committed to record interesting things I learn about development, or want to revisit.

### July 8, 2019
* docker-compose can do [variable substitution](https://docs.docker.com/compose/compose-file/#variable-substitution) based on a `.env` file
* Docker can use [multi-stage builds](https://docs.docker.com/compose/compose-file/#build) to write efficient multi-layered builds that pass only desired artifacts between layers.

### July 9, 2019
* When you open a file with vim, a `.swp` suffixed copy is created that represents unsaved changes. It won't be cleaned up if vim exits abnormally.
* Delete the entire contents of a file with vim: `ggdG`
* Move lines vertically with vim: `:m+` and `:m-2`
* docker-compose.*.yml files can be stacked in varying combinations to achieve different environments. [Relevant Article](https://medium.com/vteam/configure-docker-project-for-different-environments-using-docker-compose-3-bfbef37d951c)

### July 11, 2019
* Certbot's github features preferred [nginx config](https://raw.githubusercontent.com/certbot/certbot/master/certbot-nginx/certbot_nginx/options-ssl-nginx.conf) for SSL encrypted web service. Developers can include this in their nginx config via the [include directive](https://raw.githubusercontent.com/certbot/certbot/master/certbot-nginx/certbot_nginx/options-ssl-nginx.conf).

### July 16, 2019
* In Javascript, the `new` keyword can be used on any function to treat it as a constructor. By assigning properties to `this` inside the function, you'll return an object with methods that can affect one another without having to use the `class` keyword.

### July 18, 2019
* When using the linux `ssh` and `sftp` commands, you can use the `-b` flag to indicate a batchfile that to execute your remote commands.

### July 19, 2019
* `rsync` is a great alternative to `sftp` in many cases, because it will only transfer files that don't already exist, and can delete files that have been removed in the transfer source.

### July 24, 2019
* [CSS variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) are currently supported by all major browsers. The formal term for them is "Custom Properties".
* Redis keys typically use "." or ":" for namespacing, e.g. `products.72.units_sold`, or `employees:17:salary`.
* Redis can store many types of values, not just strings. Commands like `ADD` have many counterparts like `ZADD` that correspond to different value types.
* To reset a remote git branch to a previous commit: `git reset --hard <commit-hash> && git push -f origin`
* [git reflog](https://www.atlassian.com/git/tutorials/rewriting-history/git-reflog) is useful for seeing when references were updated in the local repo. It's often a good resource for rewriting git history.
* `git stash --include-untracked` will eliminate untracked changes in your git repo`.
* [Data Attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) in the DOM can be accessed in Javascript with the syntax `element.dataset.<suffix>`, and in CSS with `attr(data-<suffix>)`.
* Brushing up occasionally on [HTML Color Values](https://www.w3schools.com/colors/colors_hex.asp) goes a long way for quick prototyping.
* `element.offsetTop` can be used to calculate the number of items in a flexbox row. [See my an example](https://codepen.io/craigfay/pen/dxXGZO)

### July 28, 2019
* In PHP, `compact()` and `list()` are analogous to Javascript's [Object Value Shorthand](https://alligator.io/js/object-property-shorthand-es6/), and [Array Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment).

### July 29, 2019
* Webkit is one of many HTML/CSS rendering engines. As of 2019, Opera, Chrome, and Microsoft have all anounced usage of [Blink](https://en.wikipedia.org/wiki/Blink_(browser_engine)), an engine based on Webkit.
* CSS properties prefixed with `-webkit-`, etc.. are indicating that the rule is only to be used by a specific engine.
* Node JS doesn't exit the process with code `1` when errors are thrown. This seems intutitive, but it's important because automated pipelines typically require a non-zero exit to indicate failure.

### July 30, 2019
* You can run one-off commands from docker-compose.yml files with `docker-compose run <service> <command>`
* Services defined in `docker-compose.yml` can use a `working_dir` attribute. This eliminates my need to use `Dockerfile` in conjunction with `docker-compose.yml` in several cases.
* In JS, you can use `Object.create()` to make an object with a null prototype. This means that it won't have any properties of default objects, making it a candidate for a [cache-like object](https://www.bennadel.com/blog/2797-creating-objects-with-a-null-prototype-in-node-js.htm).
* In ES6, you can [extend functions with classes](https://stackoverflow.com/questions/36871299/how-to-extend-function-with-es6-classes), and have a function as the result of a constructor.

### July 31, 2019
* A key consists of a modulus and an exponent. Both the public and private key use the same modulus, what differs is the exponent. To encrypt (or decrypt) you take your message, raise it to the power of the exponent, divide the modulus, and the remainder is your encrypted (or decrypted) answer. [Source](https://crypto.stackexchange.com/questions/40362/the-relationship-between-a-private-and-public-key)
* Creating HTTP Redirects is just as simple as using the right status code and adding a "location" header.

### August, 1 2019
* You can run `npm install` in a different directory with the `--prefix` flag: `npm --prefix ./src install`
* See available npm scripts with `npm run`