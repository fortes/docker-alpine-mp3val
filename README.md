# docker alpine mp3val

This is a Dockerfile for [mp3val](http://mp3val.sourceforge.net/), a command-line program for validating and fixing mp3 files.

It's built from Alpine, so it's pretty small at about 50MB. Don't get too impressed though, because the program itself is all of 40K, so it's not a great way to save disk space.

## Build from Dockerfile

```sh
git clone https://github.com/fortes/docker-alpine-mp3val
cd docker-alpine-mp3val
docker -t build docker-alpine-mp3val .
```

## Docker run example

```sh
# Fix all files in current directory in place
docker run -u "$(id -u):$(id -g)" -v $(pwd):/mp3 mp3val-test sh -c 'mp3val -f -nb /mp3/*.mp3'
```
