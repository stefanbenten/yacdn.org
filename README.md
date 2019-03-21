# yacdn.org
Yet Another CDN.

[![Build Status](https://travis-ci.org/ovsoinc/yacdn.org.svg?branch=master)](https://travis-ci.org/ovsoinc/yacdn.org)
[![Coverage Status](https://coveralls.io/repos/github/ovsoinc/yacdn.org/badge.svg?branch=master)](https://coveralls.io/github/ovsoinc/yacdn.org?branch=master)
[![License](https://img.shields.io/badge/license-AGPLv3-blue.svg?label=license)](https://github.com/Storj/ovsoinc/yacdn.org/blob/master/LICENSE)
[![CDN Hits](https://img.shields.io/badge/dynamic/json.svg?label=CDN%20Hits&url=https://yacdn.org/stats&query=$.cdnHits&colorB=green)](https://img.shields.io/badge/dynamic/json.svg?label=CDN%20Hits&url=https://yacdn.org/stats&query=$.cdnHits&colorB=green)
[![CDN Data](https://img.shields.io/badge/dynamic/json.svg?label=CDN%20Data&url=https://yacdn.org/stats&query=$.cdnData&colorB=blue)](https://img.shields.io/badge/dynamic/json.svg?label=CDN%20Data&url=https://yacdn.org/stats&query=$.cdnData&colorB=blue)
[![Cache Usage](https://img.shields.io/badge/dynamic/json.svg?label=Cache%20Usage&url=https://yacdn.org/stats&query=$.cacheStorageUsage&colorB=purple)](https://img.shields.io/badge/dynamic/json.svg?label=Cache%20Usage&url=https://yacdn.org/stats&query=$.cacheStorageUsage&colorB=purple)

## CDN

#### How to Use

By default the file will be kept in the cache for 24 hours.

```
https://yacdn.org/serve/<uri>
```

Need to refresh the object more frequently than 24 hours? You can set `maxAge` manually:

```
https://yacdn.org/serve/<uri>?maxAge=[seconds]
```

#### Example
```
https://yacdn.org/serve/http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png
```
![https://yacdn.org/serve/http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png](https://yacdn.org/serve/http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png)

## Proxy / CORS Proxy

Can also be used as an effective proxy / CORS proxy by using the proxy endpoint.

#### How to Use

```
https://yacdn.org/proxy/<uri>
```

#### Example
```
https://yacdn.org/proxy/http://meowbaari.com/wp-content/uploads/2016/06/1464933927_cat_acrobat.png
```
![https://yacdn.org/proxy/http://meowbaari.com/wp-content/uploads/2016/06/1464933927_cat_acrobat.png](https://yacdn.org/proxy/http://meowbaari.com/wp-content/uploads/2016/06/1464933927_cat_acrobat.png)

## Technical

### Running

```
$ DEBUG=yacdn:* node server
  yacdn:server Server listening on port 3000... +0ms
  yacdn:server serve#205 url: http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png +5s
  yacdn:server serve#205 referer: undefined +1ms
  yacdn:cache http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png not in cache +0ms
  yacdn:cache lock true +0ms
  yacdn:server serve#205 size: 0.02 MB +398ms
  yacdn:server serve#205 done, took 404ms +5ms
  yacdn:server serve#205 effective speed: 0.04 megabits/s +0ms
  yacdn:server serve#206 url: http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png +5s
  yacdn:server serve#206 referer: undefined +0ms
  yacdn:cache http://meowbaari.com/wp-content/uploads/2016/06/1464933654_cat_sleep.png already in cache +5s
  yacdn:server serve#206 size: 0.02 MB +2ms
  yacdn:server serve#206 done, took 2ms +0ms
  yacdn:server serve#206 effective speed: 8.64 megabits/s +0ms
```
