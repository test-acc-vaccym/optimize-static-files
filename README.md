OSF
=====================

A tool we run every night to optimise static files for faster loading times.

**With this tool we:**

1. Create .gz and .br files that are served by NGINX with [`gzip_static`](https://nginx.org/en/docs/http/ngx_http_gzip_static_module.html#gzip_static) and [`brotli_static`](https://github.com/google/ngx_brotli/blob/master/README.md);
2. Reduce the size of JPG and PNG with [jpegoptim](https://github.com/tjko/jpegoptim) and [optipng](http://optipng.sourceforge.net/).

Using this can be quite CPU intensive, especially the image optimisation part, so it is recommended to run it by night or other non-intensive traffic times.

We run this on dedicated servers with E3-1270v6 CPUs — and even then, CPU usage is somewhat insane.

## Usage
`osf <DOMAIN>`

Where `DOMAIN` is the domain you want to have optimised. The script does not overwrite original files, instead placing optimised files alongside original ones.

Keep in mind that we keep all WordPress installs under `/srv/DOMAIN/www/`, so make the necessary changes to the script if you keep them elsewhere. More specifically, you want to change directories in lines 29, 30, 33 and 34.

## Known issues
* The script does not detect if a file is optimised, meaning that running this daily waste CPU cycles;
* No error handling whatsoever.

## TODO
* Look into [WebP](https://developers.google.com/speed/webp/) conversion and ways for [NGINX to serve them conditionally](https://centminmod.com/webp/);
* Check if .gz and .br files exist and bypass optimisation if they do. We need to ignore this rule if a new version of the source file is available;
* Add error handling.
