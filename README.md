# DevDiaries

Learn how I think through development of my projects

## Docker stuff

### Building site

```console
docker run --rm --volume="$PWD:/src" -it klakegg/hugo:0.91.2-ext-ubuntu-onbuild server --minify --theme hugo-book
```

### Serving

```console
docker run --rm --volume="$PWD:/src" -p 1313:1313 -it klakegg/hugo:0.91.2-ext-ubuntu-onbuild server --minify --theme hugo-book
```
