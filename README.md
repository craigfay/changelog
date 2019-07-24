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
* 
