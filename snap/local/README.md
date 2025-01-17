### Snap integration

<https://snapcraft.io/>

snap link: <https://snapcraft.io/victoriametrics>

#### develop

Install snapcraft or docker

build snap package with command

 ```bash
make build-snap
```

It produces snap package with current git version - `victoriametrics_v1.46.0+git1.1bebd021a-dirty_all.snap`.
You can install it with command: `snap install victoriametrics_v1.46.0+git1.1bebd021a-dirty_all.snap --dangerous`

#### usage

installation and configuration:

```bash
# install
snap install victoriametrics
# logs
snap logs victoriametrics
# restart
 snap restart victoriametrics
```

Configuration management:

 Prometheus scrape config can be edited with your favorite editor, its located at

```bash
vi /var/snap/victoriametrics/current/etc/victoriametrics-scrape-config.yaml
```

after changes, you can trigger config reread with `curl localhost:8248/-/reload`.

Configuration tuning is possible with editing extra_flags:

```bash
echo 'FLAGS="-selfScrapeInterval=10s -search.logSlowQueryDuration=20s"' > /var/snap/victoriametrics/current/extra_flags
snap restart victoriametrics
```

Data folder located at `/var/snap/victoriametrics/current/var/lib/victoriametrics/`
