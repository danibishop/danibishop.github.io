# Dev

## Jekyll

Docs [here](https://github.com/envygeeks/jekyll-docker/blob/master/README.md)

### For development (it does not auto-refresh in Windows :( )

```bash
> docker run --rm --volume="$PWD:/srv/jekyll:Z" -p 4000:4000  jekyll/jekyll:4.2.0 jekyll serve
```