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