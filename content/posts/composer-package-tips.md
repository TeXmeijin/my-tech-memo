---
tags: [PHP]
title: composerで公開されていないライブラリをGitHubから直接利用する
date: 2021-09-13T23:49:53+09:00
---

https://getcomposer.org/doc/05-repositories.md#package-2

```json
 {
     "repositories": [
         {
             "type": "package",
             "package": {
                 "name": "smarty/smarty",
                 "version": "3.1.7",
                 "dist": {
                     "url": "https://www.smarty.net/files/Smarty-3.1.7.zip",
                     "type": "zip"
                 },
                 "source": {
                     "url": "http://smarty-php.googlecode.com/svn/",
                     "type": "svn",
                     "reference": "tags/Smarty_3_1_7/distribution/"
                 },
                 "autoload": {
                     "classmap": ["libs/"]
                 }
             }
         }
     ],
     "require": {
         "smarty/smarty": "3.1.*"
     }
 }
```
