# About
This is a place I've committed to record interesting things I learn about development, or want to revisit.

# Dec 14, 2019
* There are several types of physical objects that can be used as qubits for quantum computing, including photons, neutrons, and electrons.

# Dec 13, 2019
* Google awards better search result rankings to pages that use [AMP](https://amp.dev/documentation/examples/) to display their content.
* Increasingly, Google also rewards sites for having a minimal visual diff before and after asynchronous content is loaded.

# Dec 12, 2019
* When trying to connect to a remote host via ssh, it will not accept your public key if the home directory has permissions that are too liberal. [This can prevent you from using passwordless ssh](https://unix.stackexchange.com/questions/45042/server-does-not-accept-public-key-for-ssh-login-without-password). 

# Dec 11, 2019
* HTML `img` tags have an attribute called [`srcset`](https://html.com/attributes/img-srcset/), which allows you to specify which images to load based on screen size. It's comparable to functionality provided by the `picture` tag, but has wider browser support.

# Dec 10, 2019
* When running docker compose in detached mode, you can use `docker-compose logs <container_name>` to see the logs for a specific container. `docker-compose logs` has [additional options](https://dev.to/kbariotis/dont-just-docker-compose-up-gff) to view logs flexibly.
* "IIFE" is an abbreviation in the Javascript space for ["Immediately Invoked Function Expression"](https://en.wikipedia.org/wiki/Immediately_invoked_function_expression)
* In Javascript, the `void` keyword will force anything after it to be interpreted as an expression.
* The `ssh-copy-id` command can be used to automatically copy your ssh public key to a host.

# Dec 5, 2019
* In Docker Compose, service environment variables are not available to the Dockerfiles at built time. Instead, you should use the the the [`args` suboption](https://docs.docker.com/compose/compose-file/#args).

# Dec 4, 2019
* When you clone a Git repo that has submodules, you'll have to run `git submodule init`, and `git submodule update` before submodule contents will be present locally.
* Instead of using the steps listed above, you can clone a repository using `git clone --recurse-submodules` to prepare all submodules and their children.
* [Where is the source code for bash commands?](https://askubuntu.com/questions/1193743/where-to-find-the-code-for-the-terminal-commands#comment1998655_1193743) - [gnu.org](https://www.gnu.org/software/coreutils/)
* In bash, use `env` to list all current environment variables.

# Dec 3, 2019
* In SQL, you can use the [`RETURNING`](https://www.postgresql.org/docs/11/dml-returning.html) clause to modify selected data, and avoid writing multiple queries.
* "DDL" is an abbreviation for Data Definition Language, and is used mostly in reference to data persistence systems.

# Dec 2, 2019
* On Mac/Windows, Docker containers can reference the host ip with `host.docker.internal`. On linux, you must use [other methods](https://nickjanetakis.com/blog/docker-tip-65-get-your-docker-hosts-ip-address-from-in-a-container).
* Sometimes in docker, you'll get messages that indicate a lack of storage space. Removing dangling volumes and images can usually solve the problem: `docker volume ls -q -f dangling=true`, `docker rmi $(docker images -q -f "dangling=true")`

### Nov 29, 2019
* In Rust, it's almost always preferable to use `&str` in function signatures instead of `&String`, because it will work with both slices and strings.
* Ownership, borrowing, and slices are the three features of Rust that ensure memory safety at compile time.
* The preferred nomenclature for properties of a `struct` in Rust is "fields".
* In Rust, you cannot store references in a struct without [lifetimes](file:///Users/craigfay/.rustup/toolchains/stable-x86_64-apple-darwin/share/doc/rust/html/book/ch10-00-generics.html).

* In Rust, `impl` indicates an "Implementation Block", in which methods of a struct are defined.
* In Rust, methods can take ownership of `self`, borrow it mutably, or borrow it immutably. Perhaps the only realistic use of methods taking ownership of `self` is to prevent the instance from being used after the invocation.
* Rust's "automatic referencing/dereferencing" feature allows calling methods on struct references. If the compiler didn't imply referencing/dereferencing, the ownership system would make the language much less readable.
* When functions inside Rust `impl` blocks don't have `self` as a first paramter, they're called "associated functions". These functions are invoked using the `Struct::name()` syntax, and are most commonly used as constructors.

### Nov 26, 2019
* [Aspect Oriented Programming](https://flowframework.readthedocs.io/en/stable/TheDefinitiveGuide/PartIII/AspectOrientedProgramming.html) is a programming paradigm in which allows cross-cutting concerns like logging or security to be isolated from other modules.
* When working with Golang, use `go fmt` to run a formatter against your code.
* In Golang, use `reflect.TypeOf()` to get the type of a value. This is useful for determining what function signatures should be.
* In Golang, values of a package are only exported if their name is capitalized. Lowercased names within packages are essentially private.
* In Golang, the short assignment operator, `:=`, is only available within functions. Outside of functions, it's necessary to use the `var` keyword.

### Nov 25, 2019
* The [IndexDB API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) is a performant alternative to Web Storage APIs for storing large amounts of structured data in browsers.

### Nov 18, 2019
* If you want to create a new file when you are viewing Vim’s file explorer (netrw), simply hit the %. Vim will ask you for a file name, create that file in the currently viewed directory and open a buffer.

### Nov 12, 2019
* In vim, use `:b#` or `:Ex` to return to the file browser from a file.
* [Common Gateway Interface](https://whatis.techtarget.com/definition/common-gateway-interface-CGI) (CGI) is a standard that allows a webserver to pass incoming request data to an application before responding. PHP is an example of a program that might be invoked via CGI.

### Nov 11, 2019
* System languages must have two types of strings, allocated and static. This is because Static strings are best suited to living in ROM, which is cheaper materially, and also in regard to power consumption (as compared to RAM).

### Nov 5, 2019
* BIOS and UEFI are both examples of "Firmware Standards".
* Once the BIOS runs self test and initialization routines of the hardware, it looks for bootable disks. If it finds one, the control is transferred to its bootloader, which is a 512-byte portion of executable code stored at the disk's beginning.
* The Multiboot Standard was created in 1995 by the [Free Software Foundation](https://en.wikipedia.org/wiki/Free_Software_Foundation) to prevent every OS from having to implement their own Bootloader. Primarily, Multiboot describes the interface between the bootloader and the OS. Unfortunately, Multiboot is very sparsely documented.

### Nov 3, 2019
* Rust has special syntax for [Diverging Functions](https://doc.rust-lang.org/1.30.0/book/first-edition/functions.html#diverging-functions), which never return.
* [Markov Chains](https://brilliant.org/wiki/markov-chains/) are state mathematical systems for modeling probabilistic behavior over time. A Markov chain can be described with a single Stochastic Matrix, and Initialization Vector.


### Nov 1, 2019
* On Mac/Linux, use `find somefile` to locate a file/directory by name. Use `find somefile -type f` to only include files.
* Use `git cat-file -p <hash>` to examine a piece of content in the git database, if you know it's hash.

### Oct 31, 2019
* Use `nvm alias default 12` to set nvm's default version, in this case, 12.

### Oct 28, 2019
* Full Duplex communication allows signal to travel in two directions. A phone call, video chat, and the WebSockets protocol would all be considered full duplex.
* Full Duplex can be emulated with techniques like Time-Division Duplexing, or Frequency-Division duplexing, which use only a half duplex communication channel. Frequency-Division duplexing is used in ham radio operation.

### Oct 24, 2019
* Docker was originally created by dotCloud, who folded after open sourcing it. 

### September 30, 2019
* Ion is a serialization language created by Amazon. It can have both a binary, and human readable representation.
* Flatbuffers is a serialization library developed by Google that allows you to access data without unpacking it. This makes it highly memory efficient.
* [Kenneth Truyers](https://www.kenneth-truyers.net/2016/10/13/git-nosql-database/) has proposed using Git as a database solution. 
* [Base Web] is Uber's React UI Framework/Design System.
* [Kraken](https://github.com/uber/kraken) is Uber's open source Docker image management workflow.
* FreeBSD has a concept called "Jails", which is akin to Docker Containers. Although obviously less well known, FreeBSD Jails are generally considered more powerful and mature.
* When using node inside docker containers, always npm install inside the container, because binaries in node_modules will likely not work inside the container. To make sure your modules don't get into the container, add `node_modules/` to `.dockerignore`.
* Node docker images have a user called 'node', with very few privileges. In your Dockerfile, use `USER node` after you've done all your commands that require root. This will help protect you from anyone who was able to get access to your node container.
* Node, and many other scripting languages don't listen for shutdown systems in Linux. This makes managing Node processes less than ideal.

### September 20, 2019
 * In Node, the entire allocated memory is known as the "resident set".
 * In Node, use `process.memoryUsage()` to get properties associated with memory usage.

### September 15, 2019
 * Cabal (Common Architecture for Building Applications and Libraries) is Haskell's package manager.
 * `cabal sandbox init` will init a new project with a sandbox, which will install packages in the local directory to prevent dependency conflicts.

### September 14 2019
* In Bash, `date -r <filename>` will show a file's date modified. You can use [date formatting](https://linux.die.net/man/1/date) as well: `date -r <filename> "+%m-%d-%Y %H:%M:%S"`

### September 11, 2019
* [Js13kGames](https://2019.js13kgames.com) is a JavaScript coding competition for HTML5 Game Developers. The fun part of the compo is the file size limit set to 13 kilobytes. The competition started at 13:00 CEST, 13th August and will end at 13:00 CEST, 13th September 2019. 
* [Apache Arrow](https://arrow.apache.org/) is a cross-language development platform for in-memory data. There are some very serious advantages to this idea, namely that IO based tasks, along with serialization will be drastically reduced where not eliminated.

### September 10, 2019
* An [erasure code](https://en.wikipedia.org/wiki/Erasure_code) takes a “message,” such as a data file, and makes a longer message in a way that the original can be reconstructed from the longer message even if parts of the longer message have been lost. [Reed-Solomon](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction) is an erasure code with exactly the properties we needed for file storage, and it is simple and straightforward to implement. [Source](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction)
* A [Time Series Database](https://www.influxdata.com/time-series-database/) is a database concerned with monitoring time-centric data. A TSDB should support storing high precision data for short periods of time, but necessarily downsample data over longer periods of time.
* [FaunaDB](https://fauna.com/) is recently recognized as a leader in "serverless" data persistence. This means they'll host your database, manage scaling, and provide all the usual web APIs for interacting with it.

### September 8, 2019
* Facebook uses a PHP component syntax called XHP, which is a wrapper for a library called UIComponent, that features DOM-like classes to construct an HTML tree. It's stylistically similar, and a precursor to React/JSX.
* [XHP](https://docs.hhvm.com/hack/XHP/some-basics) allows UI code to be typechecked, and automatically avoids several common issues such as cross-site scripting (XSS) and double-escaping.

### September 7, 2019
* On Linux, the `apt` command is being recommended by distros as an alternative to `apt-get` and `apt-cache`. It's essentiall a wrapper for the afforementioned commands, but with smaller surface area.
* Starting with docker 0.6.5, you can add -t to the docker run command, which will attach a pseudo-TTY. Then you can type Control-C to detach from the container without terminating it.
* There are a number of problems with using docker within docker. The preferred method is to invoke the host's docker from within containers to create sibling containers.

### September 6, 2019
* In Javascript, it's not uncommon to assign `const self = this`. This makes the designated `this` referenceable even when there may be another `this` in a more narrow scope.

### September 4, 2019
* Helpful prequisites for Machine Learning:
  * Gradient Descent
  * Linear Regression
* Feature Columns are the preferred way of defining input to TensorFlow.
* "One Hot Encoding" is a way of encoding enum-like values with boolean switches.
* A polynomial expression can only use arithmetic operations and non-negative integer exponents on variables.
* Polynomials cannot feature division by a variable.
* The word "polynonomial" derives from the phrase "many terms".

### September 3, 2019
* "ReLU" is an abbreviation for "Rectified Linear Units". ReLU activation functions overcome the vanishing gradient problem, which allows machine learning models to learn faster and perform better.
* In Chrome, `CMD SHIFT T` re-opens the last tab that was closed.

### September 2, 2019
* vJoy is a great Windows specific program for emulating hardware input.
* Node's `fs.watch` has several fatal weaknesses. The package [chokidar](https://www.npmjs.com/package/chokidar) is a great substitute.
* Tensorflow is not uniquely suited to machine learning, but can be used to define any mathematical computation as a data flow graph.
* "Tensor" refers to a multidimensional Array.
* In Tensorflow, the nodes in the graph are operations, and the edges are Tensors.
* A machine learning algorithm can be divided conceptually into 5 parts:
  * Training Data
  * Model
  * Cost Function
  * Optimization Objective
  * Evaluation Criteria
* The "Layers API" is Tensorflow's primary interface for building models. The "Estimator API" is a higher level surface area that exposes frameworks for building machine learning algorithms.
* One level higher, "Canned Estimators" can be thought of as models in a box.
  * The three estimators provided "Canned" in Tensorflow core are "Linear Regression", "Logistic Regression", and "Deep Neural Network".

### August 30, 2019
* Docker may give an error approximating: `cannot find available IPv4 address`. You can fix this with `docker network prune`.

### August 29, 2019
* In Docker, `docker-compose run --rm <service> <command>` will remove the container after it finishes executing the command.
* In Docker, `docker-compose run <service> <command>` does not automatically publish container ports to the host. Use `-p`
* In Docker, `docker-compose run --service-ports <service> <command>` will publish the specified service ports to the host.
* Use `docker build -t <name> .` to build and tag a container from a Dockerfile in the current directory. "Tag" just means that you specify the container name.
* The `-i` in `docker run -i` is short for "interactive".

### August 28, 2019
* Prisma uses an "application schema" that describes what will be exposed to clients.

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
