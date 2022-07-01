# This repo reproduces renovate bug renovatebot/renovate#16342

This repo is to demonstrate a strange behavior/bug with renovate and
the gradle manager. The gradle manager fails to extract/detect dependecies
if the version numbers are not maven compliant. From the example package
names within the `build.gradle.kts` fil,e only the one with a compliant
version is extracted.

Even overwriting the versioning schema with a package rule is not working.
See `renovate.json` ...

To reproduce the bug renovatebot/renovate#16342 clone this repo and run:

```shell
export RENOVATE_TOKEN=xxxxxxxx
docker run --rm \
  -e RENOVATE_TOKEN \
  -e LOG_LEVEL=debug \
  -v "$(pwd)/renovate-config.js:/usr/src/app/config.js" \
  renovate/renovate:32.76.0
```
