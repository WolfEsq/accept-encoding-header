# Specify a Vary: Accept-Encoding Header

![Minimum PHP Version](https://img.shields.io/badge/php-%3E%3D%205.2-8892BF.svg)
![GitHub license](https://img.shields.io/badge/license-GPL_2-blue.svg)

#### [Download from the WordPress Plugin Repository](https://wordpress.org/plugins/specify-a-vary-accept-encoding-header/)

Contributors: WolfEsq
Tags: performance,security,speed,vary,accept,encoding,header  
Requires at least: 3.0.1  
Tested up to: 4.9.8  
Requires PHP: 5.2  
Stable tag: 1.0.0  
License: GPL v2+  
License URI: https://www.gnu.org/licenses/gpl-2.0.html  

## Description
Many WordPress performance plugins are bloated and include features that you don't need. This plugin does just one thing. It adds a "Vary: Accept-Encoding Header" to boost website performance.

When browsers make a request, they include HTTP headers for the server to decide what to send back. The Vary header describes what information identifies a request. Caches should only be used if the request matches the Vary information in the cache.

This plugin adds a rewrite rule to your WordPress directory's `.htaccess` Apache file.

```
<IfModule mod_headers.c>
    <FilesMatch \".(js|css|xml|gz|html)$\">
        Header append Vary: Accept-Encoding
    </FilesMatch>
</IfModule>
```

## Installation
No configuration required.

This plugin can be installed directly through your WordPress Plugins dashboard.
Click “Add New” and Search for “Vary: Accept-Encoding Header”. 

Then Install and Activate.

Alternatively, you can download the plugin using the download button on this page and then upload the `specify-a-vary-accept-encoding -header` folder to the `/wp-content/plugins/` directory then activate through the Plugins dashboard in WordPress.

## Frequently Asked Questions
### Why might this plugin not work for me?
There are a couple of reasons why this may not work for you.
If your server is running NGINX, you will probably need to update the NGINX  configuration. This can't be done from within WordPress itself. The primary NGINX configuration file is `/etc/nginx/nginx.conf`. Add this code to the file: `gzip_vary on`.
Also, this will only work for requests that are on your server. If you have third party requests, there is nothing you can do because you don’t have access to their web servers.

## Screenshots

1. Example Page Speed Scores before installing
![Example Page Speed Scores before installing](https://ps.w.org/specify-a-vary-accept-encoding-header/assets/screenshot-1.png?rev=1857583)

2. Example Page Speed Scores after installation of this plugin
![Example Page Speed Scores after installation of this plugin](https://ps.w.org/specify-a-vary-accept-encoding-header/assets/screenshot-2.png?rev=1857583)

## Changelog ##
### 1.0.1 ###
* Switch to using output buffering to prepare rule.

### 1.0 ###
* Initial release