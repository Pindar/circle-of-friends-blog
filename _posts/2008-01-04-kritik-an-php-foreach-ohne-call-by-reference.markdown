---
layout: post
status: publish
published: true
title: 'Kritik an PHP: foreach ohne call-by-reference'
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
wordpress_id: 41
wordpress_url: http://www.pindarsign.de/webblog/?p=41
date: '2008-01-04 23:26:09 +0100'
date_gmt: '2008-01-04 22:26:09 +0100'
categories:
- Technik
- code
tags:
- php
- code
- help
comments:
- id: 218
  author: NimroT
  
  author_url: ''
  date: '2008-01-11 14:02:52 +0100'
  date_gmt: '2008-01-11 13:02:52 +0100'
  content: Da haben die PHP-Entwickler wohl wieder von ISO C abgekupfert und sich
    ein bischen verlesen ;-)
- id: 221
  author: Ben
  
  author_url: http://benediktlang.de
  date: '2008-02-10 20:38:09 +0100'
  date_gmt: '2008-02-10 19:38:09 +0100'
  content: "Jop, allerdings ein gutes Thema.\r\nDamit hatte ich schon sehr oft zu
    k&Atilde;&curren;mpfen =)\r\nBesonders meine Timegrid anwendung (kalenderartig)
    hab ich damals mit while und referenz und reset erledigt =)\r\nZeit ist Geld und
    Geld ist leider begrenzt ... jetzt l&Atilde;&curren;uft das schei&Atilde;&Yuml;
    teil so ewig langsam das ich garnimma klar komm.\r\nDa zeiten um 00h getrennt
    werden m&Atilde;&frac14;ssen zb dadurch mit referenz aufbestehendes array schreiben,
    was aber wenn die folgezeit die rauskam auch &Atilde;&frac14;ber mehr als 24 stunden
    geht? ergo reset und nochmal von vorne. Wusste damals auch keine sch&Atilde;&para;nere
    l&Atilde;&para;sung, hast du ne idee =)"
- id: 842
  author: Seb
  
  author_url: ''
  date: '2008-05-08 14:51:47 +0200'
  date_gmt: '2008-05-08 13:51:47 +0200'
  content: "\"Bedauerlicherweise ist auch ein PHP-typisches &acirc;&euro;&oelig;&amp;&acirc;&euro;\x9D
    vor der Variable zur referentiellen &Atilde;&oelig;bergabe in diesem Sprachkonstrukt
    nicht erlaubt&acirc;&euro;&brvbar;\"\r\n\r\ndoch, ist es:\r\n\r\nforeach($items
    as &amp;$item ) {\r\n  &#47;&#47; $item is a Reference \r\n}\r\n\r\nforeach($items
    as $item ) {\r\n  &#47;&#47; $item is a Copy \r\n}"
- id: 843
  author: Pindar
  
  author_url: http://www.pindarsign.de
  date: '2008-05-08 15:28:09 +0200'
  date_gmt: '2008-05-08 14:28:09 +0200'
  content: "@Seb:\r\n\r\nDer Trick mit dem & geht leider erst ab PHP Version 5, siehe
    Auszug aus der offiziellen Doku:\r\n\r\n\"Beginnend mit PHP 5 k&Atilde;&para;nnen
    Sie die Arrayelemente einfach &Atilde;&curren;ndern wenn Sie der $value Variable
    ein & voranstellen. Hierdurch werden die Elemente per reference zugewiesen und
    nicht als Kopie des Wertes.\"\r\n(http:&#47;&#47;de2.php.net&#47;manual&#47;de&#47;control-structures.foreach.php)"
- id: 39793
  author: Guido
  
  author_url: ''
  date: '2009-06-22 19:38:04 +0200'
  date_gmt: '2009-06-22 17:38:04 +0200'
  content: "So geht es (PHP  $item) {\r\n  $itemRef =&amp; $items[$key];\r\n  ...\r\n}"
- id: 39805
  author: lemyaskin
  
  author_url: http://www.google.com/
  date: '2009-09-23 04:58:05 +0200'
  date_gmt: '2009-09-23 02:58:05 +0200'
  content: lemyaskin rulezz
- id: 39830
  author: Martin Abraham
  
  author_url: http://mabraham.de
  date: '2010-11-20 20:16:11 +0100'
  date_gmt: '2010-11-20 19:16:11 +0100'
  content: "Bitte bei der Verwendung von Referenzen in PHP unbedingt bedenken, die
    Referenz mit unset($ref) wieder freizugeben, auch nach foreach-Loops!!! In PHP
    gibt es keinen Block-Scope!!!\r\n\r\nhttp:&#47;&#47;schlueters.de&#47;blog&#47;index.php?url=archives&#47;141-References-and-foreach.html&amp;serendipity%5Bcsuccess%5D=moderate"
- id: 39833
  author: Martin Aulich
  
  author_url: http://martin-aulich.de
  date: '2011-01-22 13:01:39 +0100'
  date_gmt: '2011-01-22 12:01:39 +0100'
  content: "Im &Atilde;&oelig;brigen ist es auch &Atilde;&frac14;ber:\r\n\r\nforeach($array
    as $k => $v) {\r\n $array[$k] = $v.\" editiert\";\r\n}\r\n\r\nzu realisieren."
---
<p>Wie gerne nutzt man <em>foreach<&#47;em>-Schleifen, sie sind praktisch, da man dadurch sicher wei&Atilde;&Yuml;, dass man keine Endlosschleife verursacht (da man Elemente in endlicher Zeit auch nur endlich bef&Atilde;&frac14;llen kann) und da man sicher alle Elemente erreicht. Genau diese Vorteile wollte ich ebenfalls in PHP nutzen und &Atilde;&frac14;ber ein Array iterieren. Doch leider kann man so nichts in den Array-Elementen &Atilde;&curren;ndern. Die Zugriffsvariable ist nicht, wie man vielleicht erwarten w&Atilde;&frac14;rde eine Referenz auf das eigentliche Element in der Liste, die man gerade durchl&Atilde;&curren;uft, sondern sie ist eine echte Kopie davon. Folglich werden alle &Atilde;&bdquo;nderungen auch nur in die Kopie gemacht und nachdem die Schleife fertig ist, sind alle &Atilde;&bdquo;nderungen wieder vollst&Atilde;&curren;ndig verschwunden. Wieso hier nicht call-by-reference, wie in anderen Sprachen auch, angewendet wird entzieht sich meiner Kenntnis. Bedauerlicherweise ist auch ein PHP-typisches "&" vor der Variable zur referentiellen &Atilde;&oelig;bergabe in diesem Sprachkonstrukt nicht erlaubt...<&#47;p></p>
<p>Also nicht verzweifeln, sondern <em>for<&#47;em> und <em>while<&#47;em> Schleifen in PHP statt <em>foreach <&#47;em>verwenden!<&#47;p></p>
