## Docker Kosmtik Ubuntu

Docker image running Kosmtik on Ubuntu 16.04 with fonts.
Since changes in mapnik requiring `libstdc++-5-dev`, one of the Kosmtik Docker images
started failing to build. `libstdc++-5-dev` is included in Ubuntu 16.04, so this
image is based off of that.

As a bonus, it includes all Kosmitk plugins and DejaVu fonts for your rendering needs.

### Usage

Serve:

```
$ docker run -d \
    -p 6789:6789 \
    -v <project dir>:/opt/project \
    nathancahill/kosmtik \
    kosmtik serve /opt/project/<project.(mml|yml)> --host 0.0.0.0
```

Export:

```
$ docker run -v <project dir>:/opt/project
    nathancahill/kosmtik \
    kosmtik export /opt/project/<project.(mml|yml)> --format tiles --output /opt/project/<tiles>
```

Refer to [Kosmtik Usage](https://github.com/kosmtik/kosmtik#usage) for more server options,
or [Kosmtik Tile Export](https://github.com/kosmtik/kosmtik-tiles-export/blob/master/index.js) for more export options.
