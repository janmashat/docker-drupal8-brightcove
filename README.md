docker-drupal8-brightcove
==============

This is a recipe for building a [Docker](https://www.docker.com/) container with Drupal 8 and the latest Brightcove module (8.x-1.x), including Linux (Debian 8), Apache and MySQL.
Before building, make sure you have [Docker Engine](https://docs.docker.com/engine/installation/) installed.

Based on: https://github.com/ricardoamaro/docker-drupal

Note: in order for uploading to work, the Drupal site must be accessible from the internet - because uploaded videos/images/captions are first stored on your Drupal site before being retrieved by Brightcove.

### How to use:

```sh
git clone https://github.com/janmashat/docker-drupal8-brightcove.git
cd docker-drupal8-brightcove

docker build -t drupal8-brightcove .
docker run -it --name drupal8-brightcove -p 80:80 -p 9001:9001 drupal8-brightcove
```

If you would like to store the docroot on the host:

```sh
docker run -it --name drupal8-brightcove -p 80:80 -p 9001:9001 -v path_on_the_host:/var/www drupal8-brightcove
```
