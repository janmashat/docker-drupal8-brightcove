docker-drupal8-brightcove
==============

Docker image for Drupal 8 with latest Brightcove module (8.x-1.x).

Based on: https://github.com/ricardoamaro/docker-drupal

Note: the Drupal site must be accessible from the internet in order for uploading to work (Brightcove pulls uploaded videos/images/captions)

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
