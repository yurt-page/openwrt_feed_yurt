Add to `feeds.conf`:

    src-link wrt_feed_yurt /path/to/openwrt_feed_yurt

Now you need to update feeds:
```sh
./scripts/feeds update -a
./scripts/feeds install -a
```
Then run `make menuconfig` and enable
* `Base System / Customize Busybox options / Network utilities / httpd`
  * `Support Common Gateway Interface (CGI)`
  * `Set REMOTE_PORT environment variable for CGI`
  * Recommended: `Support 'Ranges:' header`
  * Recommended: `Add Last-Modified header to response`
  * Recommended: `Enable HTTP authentication`
* `Network / Web Servers/Proxies / busybox-httpd-service`.
