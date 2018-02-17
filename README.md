# HEAD

Документация по всему, что может располагаться в теге `<head>` вашего документа

Перевод [оригинального документа](https://github.com/joshbuchea/HEAD).

## Содержание

- [Рекомендуемый минимум](#Рекомендуемый-минимум)
- [Теги](#Теги)
- [Meta](#meta)
  - [Meta: Не рекомендуется использовать](#meta-Не-рекомендуется-использовать)
- [Link](#link)
  - [Link: Не рекомендуется использовать](#link-Не-рекомендуется-использовать)
  - [Фавиконки](#Фавиконки)
- [Социальные сети](#Социальные-сети)
  - [Facebook / Open Graph](#facebook--open-graph)
  - [Facebook / Instant Articles](#facebook--instant-articles)
  - [Twitter](#twitter)
  - [Google+ / Schema.org](#google--schemaorg)
  - [OEmbed](#oembed)
- [Браузеры / Операционные системы](#Браузеры--Операционные-системы)
  - [Apple iOS](#apple-ios)
  - [Apple Safari](#apple-safari)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
  - [Microsoft Internet Explorer: Устаревшее](#microsoft-internet-explorer-Устаревшее)
- [Браузеры (Китайские)](#Браузеры-Китайские)
  - [360 Browser](#360-browser)
  - [QQ Mobile Browser](#qq-mobile-browser)
  - [UC Mobile Browser](#uc-mobile-browser)
- [Ссылки на мобильные приложения](#Ссылки-на-мобильные-приложения)
- [Примечания](#Примечания)
  - [Производительность](#Производительность)
- [Дополнительные ссылки](#Дополнительные-ссылки)
- [Схожие проекты](#Схожие-проекты)
- [Другие форматы](#Другие-форматы)
- [Переводы](#Переводы)
- [Коммьюнити](#Коммьюнити)
- [Авторы](#Авторы)
- [Лицензия](#Лицензия)

## Рекомендуемый минимум

```html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!-- Эти 3 тега *должны* быть указаны в начале тега `<head>` -->
<title>Заголовок страницы</title>
```

## Теги

``` html
<!-- Заголовок страницы -->
<title>Заголовок страницы</title>

<!-- Базовый URL, который будет использоваться во всех относительных URL на странице -->
<base href="https://example.com/page.html">

<!-- Внешний CSS -->
<link rel="stylesheet" href="styles.css">

<!-- CSS внутри документа -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="script.js"></script>
<noscript><!-- Контент, который будет отображаться пользователям без javascript --></noscript>
```

## Meta

``` html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- Эти 3 meta-тега *должны* быть расположены первыми в `<head>` -->

<!-- Позволяет указывать, откуда могут грузиться ресурсы -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">
<!-- Необходимо разместить как можно выше -->
<!-- Правило применяется только к содержимому, следующему за этим тегом -->

<!-- Имя веб-приложения (следует указывать только в случае, если сайт используется как приложение) -->
<meta name="application-name" content="Application Name">

<!-- Короткое описание страницы (ограничение — 150 символов) -->
<!-- *Иногда* содержимое meta-тега `description` используется поисковыми системами как сниппет (короткое описание страницы) в выдаче -->
<meta name="description" content="Описание страницы">

<!-- Контролирует поведение поисковых систем при индексации страницы -->
<meta name="robots" content="index,follow,noodp"><!-- Все поисковые системы -->
<meta name="googlebot" content="index,follow"><!-- Указание отдельно для Google -->

<!-- Позволяет указать Google не показывать в поисковой выдаче поле для поиска по сайту -->
<meta name="google" content="nositelinkssearchbox">

<!-- Позволяет указать Google не предлагать перевести эту страницу -->
<meta name="google" content="notranslate">

<!-- Подтверждает авторство страницы в Google Search Console -->
<meta name="google-site-verification" content="verification_token">

<!-- Используется для указания ПО, которое сгенерировало эту страницу -->
<meta name="generator" content="program">

<!-- Короткое описание тематики вашего сайта -->
<meta name="subject" content="тематика вашего сайта">

<!-- 
Очень короткое предложение (до 10 слов), описывающее назначение сайта. 
Используется преимущественно для академических работ 
-->
<meta name="abstract" content="">

<!-- Полный URL страницы -->
<meta name="url" content="https://example.com/">

<meta name="directory" content="submission">

<!-- Полное доменное имя или адрес -->
<meta name="url" content="https://example.com/">

<!-- Указывает что контент сайта соответствует возрастному рейтингу `General` -->
<meta name="rating" content="General">

<!-- Позволяет контролировать процесс передачи реферальных данных  -->
<meta name="referrer" content="never">

<!-- Отключает автоматическое определение и форматирование телефонных номеров -->
<meta name="format-detection" content="telephone=no">

<!-- Полностью отключает предзагрузку DNS-адресов -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- Сохраняет cookie в веб-браузере для клиентской аутентификации -->
<meta http-equiv='set-cookie' content='name=value; expires=date; path=url'>

<!-- Определяет, то, что страница должна грузиться в определённом фрейме -->
<meta http-equiv="Window-Target" content="_value">

<!-- Geo-теги -->
<meta name="ICBM" content="latitude, longitude">
<meta name="geo.position" content="latitude;longitude">
<meta name="geo.region" content="country[-state]"><!-- Country code (ISO 3166-1): mandatory, state code (ISO 3166-2): optional; eg. content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town"><!-- eg. content="New York City" -->
```

- [Улучшение сетевой безопасности с помощью Content Security Policy](https://habrahabr.ru/company/nixsolutions/blog/271575/)
- [Meta tags that Google understands](https://support.google.com/webmasters/answer/79812?hl=en)
- [WHATWG Wiki: MetaExtensions](https://wiki.whatwg.org/wiki/MetaExtensions)
- [ICBM on Wikipedia](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- [Geotagging on Wikipedia](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

### Meta: Не рекомендуется использовать
Meta-теги, которые не рекомендуется использовать т. к. они или устарели, или имеют малое применение:

```html
<!-- Тег использовался для указания языка страницы, но не поддерживается в полной мере. Рекомендуется использование <html lang=""> -->
<meta name="language" content="en">

<!-- Google игнорирует это содержимое, а Bing расценивает это как признак спама -->
<meta name="keywords" content="ключевые,слова,разделённые,запятыми,без,пробелов">
<!-- Нет подтверждения, что хотя бы одна поисковая система использует этот тег -->

<meta name="revised" content="Sunday, July 18th, 2010, 5:15 pm">

<!-- Даёт простой способ спам-ботам собирать email-адреса -->
<meta name="reply-to" content="email@example.com">

<!-- Лучше использовать тег <link rel="author"> или файл humans.txt -->
<meta name="author" content="name, email@example.com">
<meta name="designer" content="">
<meta name="owner" content="">

<!-- Указывает поисковым ботам, когда нужно будет переиндексировать эту страницу. Не поддерживается, т. к. поисковые системы используют случайные интервалы для переиндексации страницы -->
<meta name="revisit-after" content="7 days">

<!-- Указывает через сколько времени и на какой адрес браузер должен осуществить редирект -->
<!-- W3C не рекомендует использование этого тега. Google рекомендует использовать 301 редирект на сервере -->
<meta http-equiv="refresh" content="300; url=https://example.com/">

<!-- Тематика вашего сайта -->
<meta name="topic" content="">

<!-- Краткое описание компании или предназначения сайта -->
<meta name="summary" content="">

<!-- Устаревший тег, т. к. он указывает на то же, что и meta-тег keywords -->
<meta name="classification" content="business">

<!-- Уточняет, что ваш сайт будет отображаться для всех стран и всех языков -->
<meta name="coverage" content="Worldwide">

<!-- Контролирует то, что пользователь может получить доступ в Интернете -->
<meta http-equiv="Pics-label" content="value"> 

<!-- Управление кешированием -->
<!-- Будет лучше, если вы настроите управление кешем на стороне сервера  -->
<meta http-equiv="Expires" content="0">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Cache-Control" content="no-cache">
```

## Link

``` html
<!-- Позволяет избежать дублирование индексации контента -->
<!-- http://www.searchengines.ru/kak_pravilno_is_rel_canonical.html -->
<link rel="canonical" href="https://example.com/2010/06/9-things-to-do-before-entering-social-media.html">

<!-- Короткая ссылка на документ. Не рекомендуется к использованию, т. к. может порождать дубли страниц при индексации -->
<link rel="shortlink" href="https://example.com/?p=42">

<!-- Ссылка на AMP-версию -->
<!-- https://support.google.com/webmasters/answer/6340290?hl=ru -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html">

<!-- Ссылка на CSS-файл -->
<link rel="stylesheet" href="https://example.com/styles.css">

<!-- Ссылка на JSON-файл, который описывает установку веб-приложения -->
<link rel="manifest" href="manifest.json">

<!-- Ссылка на автора документа -->
<link rel="author" href="humans.txt">

<!-- Cсылка на страницу с авторскими правами, согласно которым предоставляется текущий документ -->
<link rel="copyright" href="copyright.html">

<!-- Ссылка на другую языковую версию документа -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- Информация об авторе -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- Ссылка на документ, который содержит архивную ссылку на текущий документ -->
<link rel="archives" href="https://example.com/2003/05/" title="May 2003">

<!-- Ссылка на документ выше (относительно иерархии сайта) -->
<link rel="index" href="https://example.com/" title="Cassius Clay">

<!-- Ссылка на начало текущего документа (например, на первую страницу статьи) -->
<link rel="start" href="https://example.com/books/winnie_the_pooh/part1/" title="Pattern Recognition 1">

<!-- Ссылка на предыдущую страницу текущего документа -->
<link rel="prev" href="https://example.com/opensearch/opensearch-and-openid-a-sure-way-to-get-my-attention/" title="OpenSearch and OpenID? A sure way to get my attention.">

<!-- Ссылка на сам ресурс (ссылка "на себя"). Данная ссылка может, например, понадобиться для обращения к документу, если его описание было получено в составе коллекции -->
<link rel="self" type="application/atom+xml" href="https://example.com/atomFeed.php?page=3">

<!-- Ссылка на первую, следующую, предыдущую и последнюю страницы документа -->
<link rel="first" href="https://example.com/atomFeed.php">
<link rel="next" href="https://example.com/atomFeed.php?page=4">
<link rel="prev" href="https://example.com/atomFeed.php?page=2">
<link rel="last" href="https://example.com/atomFeed.php?page=147">

<!-- Используется когда используется сторонний сервис для редактирования блога -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- Указывает адрес пингбэк-сервера -->
<!-- Как поясняется в спецификации, «пингбэк» это способ для блога автоматически оповещать сайты, ссылающиеся на него. Это создает обратную связь — способ пройти назад по цепочке ссылок вместо «прямого прохода». В блогах, частности WordPress, пингбэк-механизм используется для уведомления авторов, что вы ссылаетесь на кого-то при создании новой записи -->
<link rel="pingback" href="https://example.com/xmlrpc.php">

<!-- Уведомляет URL, когда вы ссылаетесь на него на вашем сайте -->
<link rel="webmention" href="https://example.com/webmention">

<!-- Загружает внешний HTML-файл в текущий файл -->
<link rel="import" href="component.html">

<!-- Open Search -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Поисковый запрос">

<!-- Фиды -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- Prefetching, preloading, prebrowsing -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="https://example.com/">
<link rel="subresource" href="styles.css">
<link rel="preload" href="image.png">
<!-- Больше информации: http://prgssr.ru/development/tehniki-prefetchinga-dlya-uluchsheniya-proizvoditelnosti-sajtov.html -->
```

### Link: Не рекомендуется использовать
Link-теги, которые не рекомендуется использовать:

```html
<link rel="shortcut icon" href="path/to/favicon.ico">
```

### Фавиконки

``` html
<!-- Для IE 10 и ниже -->
<!-- Не используется ссылка, просто разместите файл, который называется favicon.ico в корне вашего сайта -->

<!-- Для IE 11, Chrome, Firefox, Safari, Opera -->
<link rel="icon" href="path/to/favicon-16.png" sizes="16x16" type="image/png">
<link rel="icon" href="path/to/favicon-32.png" sizes="32x32" type="image/png">
<link rel="icon" href="path/to/favicon-48.png" sizes="48x48" type="image/png">
<link rel="icon" href="path/to/favicon-62.png" sizes="62x62" type="image/png">
<link rel="icon" href="path/to/favicon-192.png" sizes="192x192" type="image/png">
<!-- Больше информации: https://bitsofco.de/all-about-favicons-and-touch-icons/ -->
```

- [All About Favicons (And Touch Icons)](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)

## Социальные сети

### Facebook / Open Graph

``` html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
<!-- Facebook: https://developers.facebook.com/docs/sharing/webmasters#markup -->
<!-- Open Graph: http://ogp.me/ -->
```

- [Facebook Open Graph Markup](https://developers.facebook.com/docs/sharing/webmasters#markup)
- [Open Graph protocol](http://ogp.me/)

### Facebook / Instant Articles

``` html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- URL веб-версии этой страницы -->
<link rel="canonical" href="http://example.com/article.html">

<!-- Стиль, используемый для этой страницы -->
<meta property="fb:article_style" content="myarticlestyle">
```

- [Facebook Instant Articles: Creating Articles](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- [Instant Articles: Format Reference](https://developers.facebook.com/docs/instant-articles/reference)

### Twitter

``` html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
<!-- Больше информации: https://dev.twitter.com/cards/getting-started -->
<!-- Валидация meta-тегов Twitter: https://dev.twitter.com/docs/cards/validation/validator -->
```

- [Twitter Cards: Getting Started Guide](https://dev.twitter.com/cards/getting-started)
- [Twitter Card Validator](https://dev.twitter.com/docs/cards/validation/validator)

### Google+ / Schema.org

``` html
<link href="https://plus.google.com/+YourPage" rel="publisher">
<meta itemprop="name" content="Заголовок">
<meta itemprop="description" content="Описание страницы, лимит — 200 символов">
<meta itemprop="image" content="https://example.com/image.jpg">
```

### OEmbed

``` html
<link rel="alternate" type="application/json+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- [oEmbed format](http://oembed.com/)

## Браузеры / Операционные системы

### Apple iOS

``` html
<!-- Баннер для перехода на страницу приложения в AppStore -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- Отключает автоматическое определение и форматирование телефонных номеров -->
<meta name="format-detection" content="telephone=no">

<!-- Добавить на домашний экран -->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="App Title">

<!-- Touch Icons -->
<link rel="apple-touch-icon" href="path/to/apple-touch-icon.png">
<link rel="apple-touch-icon-precomposed" href="path/to/apple-touch-icon-precomposed.png">
<!-- В большинстве случаев одной иконки размером 180×180px достаточно -->

<!-- Изображение, отображаемое при загрузке -->
<link rel="apple-touch-startup-image" href="path/to/startup.png">

<!-- Больше информации: https://developer.apple.com/safari/library/documentation/appleapplications/reference/safarihtmlref/articles/metatags.html -->
```

- [Apple Meta Tags](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

### Apple Safari

```html
<!-- Закреплённый сайт -->
<link rel="mask-icon" href="path/to/icon.svg" color="red">
```

### Google Android

``` html
<!-- Цвет темы в Chrome -->
<!-- https://developers.google.com/web/updates/2014/11/Support-for-theme-color-in-Chrome-39-for-Android?hl=en -->
<meta name="theme-color" content="#E64545">

<!-- Добавить на домашний экран -->
<meta name="mobile-web-app-capable" content="yes">
<!-- Больше информации: https://developer.chrome.com/multidevice/android/installtohomescreen -->
```

### Google Chrome

``` html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- Отключить предложение перевести страницу -->
<meta name="google" value="notranslate">
```

### Microsoft Internet Explorer

``` html
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta http-equiv="cleartype" content="on">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Отключает подсветку ссылок в IE 10 для Windows Phone (https://blogs.windows.com/buildingapps/2012/11/15/adapting-your-webkit-optimized-site-for-internet-explorer-10/) -->
<meta name="msapplication-tap-highlight" content="no">

<!-- Закреплённые сайты (https://msdn.microsoft.com/en-us/library/dn255024(v=vs.85).aspx) -->
<meta name="application-name" content="Contoso Pinned Site Caption">
<meta name="msapplication-tooltip" content="Example Tooltip Text">
<meta name="msapplication-starturl" content="/">

<meta name="msapplication-config" content="http://example.com/browserconfig.xml">

<meta name="msapplication-allowDomainApiCalls" content="true">
<meta name="msapplication-allowDomainMetaTags" content="true">
<meta name="msapplication-badge" content="frequency=30; polling-uri=http://example.com/id45453245/polling.xml">
<meta name="msapplication-navbutton-color" content="#FF3300">
<meta name="msapplication-notification" content="frequency=60;polling-uri=http://example.com/livetile">
<meta name="msapplication-square150x150logo" content="path/to/logo.png">
<meta name="msapplication-square310x310logo" content="path/to/largelogo.png">
<meta name="msapplication-square70x70logo" content="path/to/tinylogo.png">
<meta name="msapplication-wide310x150logo" content="path/to/widelogo.png">
<meta name="msapplication-task" content="name=Check Order Status;action-uri=./orderStatus.aspx?src=IE9;icon-uri=./favicon.ico">
<meta name="msapplication-task-seperator" content="1">
<meta name="msapplication-TileColor" content="#FF3300">
<meta name="msapplication-TileImage" content="path/to/tileimage.jpg">
<meta name="msapplication-window" content="width=1024;height=768">
```

### Microsoft Internet Explorer: Устаревшее

``` html
<!-- Отключает тулбар, отображаемый при наведении на изображение в IE 6 (https://msdn.microsoft.com/en-us/library/ms532986(v=vs.85).aspx) -->
<meta http-equiv="imagetoolbar" content="no">

<!-- Отключает применение темы Windows для полей ввода / кнопок (https://support.microsoft.com/en-us/kb/322240) -->
<meta name="MSThemeCompatible" content="no">

<!-- Отключает опцию, которая была доступна только в IE 6 beta (https://stackoverflow.com/q/2167301) -->
<meta name="MSSmartTagsPreventParsing" content="true">

<!-- Эффект перехода между страницами (https://msdn.microsoft.com/en-us/library/ms532847(v=vs.85).aspx) -->
<meta http-equiv="Page-Enter" content="revealtrans(duration=2,transition=2)">
<meta http-equiv="Page-Exit" content="revealtrans(duration=3,transition=12)">
<meta http-equiv="Site-Enter" content="revealtrans(duration=2,transition=2)">
<meta http-equiv="Site-Exit" content="revealtrans(duration=3,transition=12)">
```

## Ссылки на мобильные приложения

``` html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">
<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">
<!-- Web-фоллбек -->
<meta property="al:web:url" content="http://applinks.org/documentation">
<!-- Больше информации: http://applinks.org/documentation/ -->
```

- [App Links Docs](http://applinks.org/documentation/)

## Браузеры (Китайские)

### 360 Browser

``` html
<!-- Указывает движок рендеринга -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ Mobile Browser

``` html
<!-- Блокирует изменение ориентации страницы, устанавливая указанную -->
<meta name="x5-orientation" content="landscape/portrait">
<!-- Страница будет показана в полноэкранном режиме -->
<meta name="x5-fullscreen" content="true">
<!-- Страница будет отображаться в режиме "Приложение" -->
<meta name="x5-page-mode" content="app">
```

### UC Mobile Browser

``` html
<!-- Блокирует изменение ориентации страницы, устанавливая указанную -->
<meta name="screen-orientation" content="landscape/portrait">
<!-- Страница будет показана в полноэкранном режиме -->
<meta name="full-screen" content="yes">
<!-- Браузер будет отображать изображения даже если включён "текстовый режим" -->
<meta name="imagemode" content="force">
<!-- Страница будет отображаться в режиме "Приложение" -->
<meta name="browsermode" content="application">
<!-- Отключает "ночной режим" для этой страницы -->
<meta name="nightmode" content="disable">
<!-- Упрощает страницу для уменьшения потребления трафика -->
<meta name="layoutmode" content="fitscreen">
<!-- Отключает опцию масштабирования шрифтов в случае, если на странице присутствует большое количество текста -->
<meta name="wap-font-scale" content="no">
```

- [UC Browser Docs](http://www.uc.cn/download/UCBrowser_U3_API.doc)

## Примечания

### Производительность
Перенос атрибута `href` в начало тега улучшает степень сжатия, в случае, если используется GZIP. Это происходит потому что атрибут `href` используется в тегах `a`, `base` и `link`.

Пример:
``` html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
```

## Дополнительные ссылки

- [HTML5 Boilerplate Docs: The HTML](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- [HTML5 Boilerplate Docs: Extend and customize](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

## Схожие проекты

- [HTML HEAD шаблоны для Atom](https://github.com/joshbuchea/atom-html-head-snippets) - Библиотека шаблонов тега `HEAD` для редактора Atom
- [HTML HEAD шаблоны для Sublime Text](https://github.com/marcobiedermann/sublime-head-snippets) - Плагин с шаблонами тега `HEAD` для Sublime Text
- [head-it](https://github.com/hemanth/head-it) - CLI-утилита, генерирующая шаблоны тега `HEAD`
- [vue-head](https://github.com/ktquez/vue-head) - Управление мета-информацией тега `HEAD` для Vue.js

## Другие форматы

- [PDF](https://gitprint.com/konfuze/HEAD/blob/master/README.md)

## Переводы

- 🇺🇸 [Английский](https://github.com/joshbuchea/HEAD) (оригинал)
- 🇧🇷 [Бразильский вариант португальского языка](https://github.com/Webschool-io/HEAD)
- 🇨🇳 [Китайский (упрощенный)](https://github.com/Amery2010/HEAD)
- 🇮🇹 [Итальянский](https://github.com/Fakkio/HEAD)
- 🇯🇵 [Японский](http://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- 🇰🇷 [Корейский](https://github.com/Lutece/HEAD)
- 🇹🇷 [Турецкий](https://github.com/mkg0/HEAD)

## Коммьюнити

Вы можете дополнить или откорректировать этот документ открыв pull request или создав issue. 

### Участники

[Люди](https://github.com/joshbuchea/HEAD/graphs/contributors), принявшие участие в создании оригинального документа.

## Авторы

- **[Josh Buchea](http://joshbuchea.com/)** — оригинальный документ
- **[Артём Корсунов](https://github.com/konfuze)** — русский перевод

## Лицензия

[Лицензия CC0](LICENSE)

![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")
