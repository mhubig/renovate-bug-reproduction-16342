# This repo reproduces renovate bug #16342

To reproduce #16342 clone this repo an run:

```shell
docker run --rm \
  -e LOG_LEVEL=debug \
  -v "$(pwd)/renovate-config.js:/usr/src/app/config.js" \
  renovate/renovate:32.76.0
```
