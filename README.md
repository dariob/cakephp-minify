# Cakeminify plugin for CakePHP

>combine and compress your web asset resource in cakephp3+


## Installation

You can install this plugin into your CakePHP application using [composer](http://getcomposer.org).

The recommended way to install composer packages is:

```
composer require dariob/minicake

```

Load plugin in bootstrap.php

```php
Plugin::load('Cakeminify');
```



##Config

config your asset resource, create a config file named
minify.php in config directory。
or use Cake/Configure class to set minify configuration in bootstrap.php


```php
return[
    'minjs'=>[
       'source'=>[
           '/asset/jquery/dist/jquery.js',
           '/asset/zui/dist/js/zui.js',
           '/asset/vue/dist/vue.js'
       ],
       'desc'=>'/dist/main.js'
    ],
    'mincss'=>[
       'source'=>[
           '/asset/zui/dist/css/zui.css',
           '/css/view.css',
       ],
       'desc'=>'/dist/default.css'
    ],
    
];

```

##shell
combine and compress 

```shell
bin/cake minify start
```

the combine file will create in your 'desc' config


##helper

call the helper function in your template

```php
  <?= $this->minify->generateAsset() ?>
```

##output 

output is relation to the debug level

Production Mode:

```html
<link rel="stylesheet" href="/dist/default.css"/>
<script src="/dist/main.js"></script>
```
Development Mode:

```html
<link rel="stylesheet" href="/asset/zui/dist/css/zui.css"/>
<link rel="stylesheet" href="/css/view.css"/>
<script src="/asset/jquery/dist/jquery.js"></script>
<script src="/asset/zui/dist/js/zui.js"></script>
<script src="/asset/vue/dist/vue.js"></script>
```
