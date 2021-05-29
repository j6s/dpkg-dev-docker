# `thej6s/dpkg-dev` docker image

* [View on docker hub](https://hub.docker.com/r/thej6s/dpkg-dev)
* [View on github](https://github.com/j6s/dpkg-dev-docker)

A simple debian based docker image that contains dpkg-dev tools.
The sole purpose of this image is making it easier to build personal
apt repositories as outlined in this article by Guy Rutenberg:

https://www.guyrutenberg.com/2016/07/15/creating-a-personal-apt-repository-using-dpkg-scanpackages/

## Usage

```
$ docker run -u 1000 --rm \
  -v $(pwd)/packages:/workdir \
  -w /workdir thej6s/dpkg-dev \
  bash -c 'dpkg-scanpackages -m . | gzip --best > Packages.gz'
```
