docker-drupal8-brightcove
==============

This is a recipe for building a [Docker](https://www.docker.com/) container with [Drupal](https://www.drupal.org/) 8 and [Brightcove module](https://www.drupal.org/project/brightcove) 8.x-1.x in a LAMP environment (Debian GNU/Linux, Apache, MySQL).

### Prerequisites

* Before building, make sure you have [Docker Engine](https://docs.docker.com/engine/installation/) installed and running.
* For uploading to work, make sure your Drupal site is accessible from the internet (public IP address or port-forward) - because Brightcove will need to fetch all uploaded video/image/caption files from your Drupal site.

### Installation

```sh
git clone https://github.com/janmashat/docker-drupal8-brightcove.git
cd docker-drupal8-brightcove

docker build -t drupal8-brightcove .
docker run -it --name drupal8-brightcove -p 80:80 -p 9001:9001 drupal8-brightcove
```

If you would like to store the docroot on the host, use this `docker run` command instead:

```sh
docker run -it --name drupal8-brightcove -p 80:80 -p 9001:9001 -v path_on_the_host:/var/www drupal8-brightcove
```

### Usage

#### Docker
* The session will start within a GNU screen, so you can `ctrl-a c` to create a new screen.

#### Drupal

* The site will be accessible through your Docker machine's IP (usually [http://localhost/](http://localhost/) or if Docker Machine is used then it can be checked with `docker-machine ip`).
* Username/password are **admin/admin** by default, but can be changed in `start.sh` - before running `docker build`.

### Credits

Based on: https://github.com/ricardoamaro/docker-drupal
