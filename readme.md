# rss-filter

A simple PHP class for filtering RSS feeds. *Modified for filtering only passing through articles with matching words in the title, instead of filtering out articles with matching words in title or content.* 

## Usage

1] Create your `words.php` file with the words that you ~~don't~~ want to see in *titles* of the RSS feeds. *`words.php` modified and personalized for filtering MVG Störungsticker (https://ticker.mvg.de/).*

```php
<?php

$words = [
  'U2',
  'U3',
  'U6',
  'Zurzeit liegen keine Meldungen'
];
```

2] Create your `index.php` file like this.

```php
<?php

error_reporting(0);
header('Content-Type: text/xml; charset=utf-8');

include 'rss-filter.php';
$rf = new RssFilter();
echo $rf->init($_GET['source']);
```

3] Now it's time to reproduce the RSS feed.

Instead of using the original URL: *https://ticker.mvg.de/*<br>
You can use like that: *http://localhost/rss-filter/?source=https://ticker.mvg.de/*
