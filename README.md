# About
This is a place I've committed to record interesting things I learn about development, or want to revisit.

### August 26, 2019
* In Javascript, The stopPropagation() method of the Event interface prevents further propagation of the current event in the capturing and bubbling phases.

### August 20, 2019
* Node.js has a variety of issues with high-performance compression, where increased concurrency, especially on Linux, can lead to [catastrophic memory fragmentation](https://github.com/nodejs/node/issues/8871) and slow performance.
* All dimensions in React Native are unitless, and represent density-independent pixels.
* A React Native component can only expand to fill available space if its parent has dimensions greater than 0. If a parent does not have either a fixed width and height or flex, the parent will have dimensions of 0 and the flex children will not be visible.

### August 19, 2019
* You should always keep your Authorization logic outside of your GraphQL reolvers. Instead, make calls to your business logic layer.
* Don't make classes your public API. Instead, use factory functions. This will keep people from inheriting from them.
* Instead of instanceof checks, assert the existence of the methods you plan to use, and trust the user to do the right thing.
* [Abramov says](https://medium.com/@dan_abramov/youre-missing-the-point-of-react-a20e34a51e1a): React's true strength is not the Virtual DOM, but instead, composition, unidirection data flow, freedom from DSLs, explicit mutation, and static mental model.
* [Surge](https://surge.sh) is a great free host for static content.
* Robin Weiruch's detailed guide to [fetching data with React Hooks](https://www.robinwieruch.de/react-hooks-fetch-data/)
* Dan's [complete guide to useEffect()](https://overreacted.io/a-complete-guide-to-useeffect/) (React Hooks)

### August 18, 2019
* GraphQL has its own type language that’s used the write GraphQL schemas: The [Schema Definition Language](https://blog.graph.cool/graphql-sdl-schema-definition-language-6755bcb9ce51)  (SDL)
* GraphQL has a clear separation between structure and behavior. Each field in a GraphQL schema is backed by a resolver function, which determines how queries are fulfilled.
* An RPC-style (Remote Procedure Call) system is one where requesters can trigger functions remotely.
* GraphQL requests almost always succeed with a 200 even if no data was returned. Instead of HTTP error codes, they track the number of the exceptions per query.

### August 12, 2019
* In Javascript, es6 allows for dynamic property names:
 	```JS
    	const obj = {
            	[ isDog ? "dog" : "cat" ]: 'Rover'
    	}
   	```
* React Native Express features an excellent [summary of the React Component Lifecycle](http://www.reactnativeexpress.com/lifecycle_api).

### August 11, 2019
* In Vim's normal mode, `:e.` will open the file explorer, where you can use `/` to search.
* In Vim's normal mode, `:bp`will open the previously opened buffer.
* In Vim's file explorer , `d`  create directories.
* In Vim's file explorer , `%` will create a new file.
* In Vim's file explorer , `D` will delete files/directories.  
### August 10, 2019
* In Vim, `so %` will source the current file.
* In Vim, using `n` will allow you to move to the next search result.
* In Vim's normal mode, `.` will refer to the last command.
* In Vim's normal mode, `zz` will bring the current line to the center of the screen.
* In Vim's normal mode, `sp` and `vsp` will create window splits.
* In Vim's normal mode, `CTRL ww` will toggle between splits.
* In Vim's normal mode, `:ls` will show all your open buffers, AKA files. Use `b<n>` to switch to one, where `<n>` is the number of the buffer.

### August 9, 2019
* "Idempotency" describes an action that can be performed repeatedly and never perform different results. HTTP GET requests are expected to be idempotent.
* In Chrome, `OPTION CMD U` (on MacOS) will view page source.
* In the Chrome Javascript Console, the variable `$0` refers to the last element you've selected in the "Elements" tab.

### August 8, 2019
* In Javascript, `null` can be more appropriate than `undefined` as a value on an object, because `undefined` will make the object appear not to have the property that it represents.`
* In VSCode, you can toggle between the editor and file explorer with `SHIFT CMD E`.
* In Vim, `SHIFT H` and `SHIFT L` navigate to the top and bottom of the document.
* In Vim, `SHIFT J` pulls the next line onto the end of the current line.
* [Session fixation](https://en.wikipedia.org/wiki/Session_fixation) attacks attempt to exploit the vulnerability of a system that allows one person to fixate (find or set) another person's session identifier.

### August 7, 2019
* nodejs.org has an excellent recap of [HTTP Transactions in Node](https://nodejs.org/en/docs/guides/anatomy-of-an-http-transaction/). This is extremely helpful for anyone working with the built in `http` module.
* Node's `util.promisify()` will work on any function that has a callback function as its last argument if the callback accepts arguments `err, data`.
* "[Streams](https://www.freecodecamp.org/news/node-js-streams-everything-you-need-to-know-c9141306be93/) are Node's best and most misunderstood idea." - Dominic Tarr

### August 3, 2019
* By default GET requests are cacheable if there are no parameters present in the URL, a POST is not.

### August 2, 2019
* Pairing the `ts-node` module with `nodemon` can allow you to watch for file changes, while also never needing to build TypeScript modules. Use the `exec`, `ext`, and `watch` properties of `nodemon.json` to accomplish this.
* In Javascript, you can create a unique hash using `(+new Date()).toString(36)`. This doesn't guarantee uniqueness when parallel processes are using it.
* Hashes with short keys and values will be stored in a serialized manner inside Redis.

### August 1, 2019
* You can run `npm install` in a different directory with the `--prefix` flag: `npm --prefix ./src install`
* See available npm scripts with `npm run`
* See npm package dependencies with `npm ls --depth 0`
* Any npm script named with prefix "pre" or "post" will run before/after their corresponding command reference.
* Increment a package's version with `npm version` and `major`, `minor` or `patch`.
* Remove untracked git files with `git clean -f`. Preview files to be removed with `git clean -n`.
* Git allows [command aliasing](https://koukia.ca/personalizing-git-aliasing-commands-4dda73b54081).

### July 31, 2019
* A key consists of a modulus and an exponent. Both the public and private key use the same modulus, what differs is the exponent. To encrypt (or decrypt) you take your message, raise it to the power of the exponent, divide the modulus, and the remainder is your encrypted (or decrypted) answer. [Source](https://crypto.stackexchange.com/questions/40362/the-relationship-between-a-private-and-public-key)
* Creating HTTP Redirects is just as simple as using the right status code and adding a "location" header.

### July 30, 2019
* You can run one-off commands from docker-compose.yml files with `docker-compose run <service> <command>`
* Services defined in `docker-compose.yml` can use a `working_dir` attribute. This eliminates my need to use `Dockerfile` in conjunction with `docker-compose.yml` in several cases.
* In JS, you can use `Object.create()` to make an object with a null prototype. This means that it won't have any properties of default objects, making it a candidate for a [cache-like object](https://www.bennadel.com/blog/2797-creating-objects-with-a-null-prototype-in-node-js.htm).
* In ES6, you can [extend functions with classes](https://stackoverflow.com/questions/36871299/how-to-extend-function-with-es6-classes), and have a function as the result of a constructor.

### July 29, 2019
* Webkit is one of many HTML/CSS rendering engines. As of 2019, Opera, Chrome, and Microsoft have all anounced usage of [Blink](https://en.wikipedia.org/wiki/Blink_(browser_engine)), an engine based on Webkit.
* CSS properties prefixed with `-webkit-`, etc.. are indicating that the rule is only to be used by a specific engine.
* Node JS doesn't exit the process with code `1` when errors are thrown. This seems intutitive, but it's important because automated pipelines typically require a non-zero exit to indicate failure.

### July 28, 2019
* In PHP, `compact()` and `list()` are analogous to Javascript's [Object Value Shorthand](https://alligator.io/js/object-property-shorthand-es6/), and [Array Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment).

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

### July 19, 2019
* `rsync` is a great alternative to `sftp` in many cases, because it will only transfer files that don't already exist, and can delete files that have been removed in the transfer source.

### July 18, 2019
* When using the linux `ssh` and `sftp` commands, you can use the `-b` flag to indicate a batchfile that to execute your remote commands.

### July 16, 2019
* In Javascript, the `new` keyword can be used on any function to treat it as a constructor. By assigning properties to `this` inside the function, you'll return an object with methods that can affect one another without having to use the `class` keyword.

### July 11, 2019
* Certbot's github features preferred [nginx config](https://raw.githubusercontent.com/certbot/certbot/master/certbot-nginx/certbot_nginx/options-ssl-nginx.conf) for SSL encrypted web service. Developers can include this in their nginx config via the [include directive](https://raw.githubusercontent.com/certbot/certbot/master/certbot-nginx/certbot_nginx/options-ssl-nginx.conf).

### July 9, 2019
* When you open a file with vim, a `.swp` suffixed copy is created that represents unsaved changes. It won't be cleaned up if vim exits abnormally.
* Delete the entire contents of a file with vim: `ggdG`
* Move lines vertically with vim: `:m+` and `:m-2`
* docker-compose.*.yml files can be stacked in varying combinations to achieve different environments. [Relevant Article](https://medium.com/vteam/configure-docker-project-for-different-environments-using-docker-compose-3-bfbef37d951c)

### July 8, 2019
* docker-compose can do [variable substitution](https://docs.docker.com/compose/compose-file/#variable-substitution) based on a `.env` file
* Docker can use [multi-stage builds](https://docs.docker.com/compose/compose-file/#build) to write efficient multi-layered builds that pass only desired artifacts between layers.
