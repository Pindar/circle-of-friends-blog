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
    kämpfen =)\r\nBesonders meine Timegrid anwendung (kalenderartig)
    hab ich damals mit while und referenz und reset erledigt =)\r\nZeit ist Geld und
    Geld ist leider begrenzt ... jetzt läuft das scheiß
    teil so ewig langsam das ich garnimma klar komm.\r\nDa zeiten um 00h getrennt
    werden müssen zb dadurch mit referenz aufbestehendes array schreiben,
    was aber wenn die folgezeit die rauskam auch über mehr als 24 stunden
    geht? ergo reset und nochmal von vorne. Wusste damals auch keine schönere
    lösung, hast du ne idee =)"
- id: 842
  author: Seb
  
  author_url: ''
  date: '2008-05-08 14:51:47 +0200'
  date_gmt: '2008-05-08 13:51:47 +0200'
  content: "\"Bedauerlicherweise ist auch ein PHP-typisches &acirc;&euro;&oelig;&amp;&acirc;&euro;\x9D
    vor der Variable zur referentiellen Übergabe in diesem Sprachkonstrukt
    nicht erlaubt&acirc;&euro;&brvbar;\"\r\n\r\ndoch, ist es:\r\n\r\nforeach($items
    as &amp;$item ) {\r\n  // $item is a Reference \r\n}\r\n\r\nforeach($items
    as $item ) {\r\n  // $item is a Copy \r\n}"
- id: 843
  author: Pindar
  
  author_url: http://www.pindarsign.de
  date: '2008-05-08 15:28:09 +0200'
  date_gmt: '2008-05-08 14:28:09 +0200'
  content: "@Seb:\r\n\r\nDer Trick mit dem & geht leider erst ab PHP Version 5, siehe
    Auszug aus der offiziellen Doku:\r\n\r\n\"Beginnend mit PHP 5 können
    Sie die Arrayelemente einfach ändern wenn Sie der $value Variable
    ein & voranstellen. Hierdurch werden die Elemente per reference zugewiesen und
    nicht als Kopie des Wertes.\"\r\n(http://de2.php.net/manual/de/control-structures.foreach.php)"
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
    gibt es keinen Block-Scope!!!\r\n\r\nhttp://schlueters.de/blog/index.php?url=archives/141-References-and-foreach.html&amp;serendipity%5Bcsuccess%5D=moderate"
- id: 39833
  author: Martin Aulich
  
  author_url: http://martin-aulich.de
  date: '2011-01-22 13:01:39 +0100'
  date_gmt: '2011-01-22 12:01:39 +0100'
  content: "Im Übrigen ist es auch über:\r\n\r\nforeach($array
    as $k => $v) {\r\n $array[$k] = $v.\" editiert\";\r\n}\r\n\r\nzu realisieren."
---
<p>Wie gerne nutzt man <em>foreach</em>-Schleifen, sie sind praktisch, da man dadurch sicher weiß, dass man keine Endlosschleife verursacht (da man Elemente in endlicher Zeit auch nur endlich befüllen kann) und da man sicher alle Elemente erreicht. Genau diese Vorteile wollte ich ebenfalls in PHP nutzen und über ein Array iterieren. Doch leider kann man so nichts in den Array-Elementen ändern. Die Zugriffsvariable ist nicht, wie man vielleicht erwarten würde eine Referenz auf das eigentliche Element in der Liste, die man gerade durchläuft, sondern sie ist eine echte Kopie davon. Folglich werden alle &Atilde;&bdquo;nderungen auch nur in die Kopie gemacht und nachdem die Schleife fertig ist, sind alle &Atilde;&bdquo;nderungen wieder vollständig verschwunden. Wieso hier nicht call-by-reference, wie in anderen Sprachen auch, angewendet wird entzieht sich meiner Kenntnis. Bedauerlicherweise ist auch ein PHP-typisches "&" vor der Variable zur referentiellen Übergabe in diesem Sprachkonstrukt nicht erlaubt...</p></p>
<p>Also nicht verzweifeln, sondern <em>for</em> und <em>while</em> Schleifen in PHP statt <em>foreach </em>verwenden!</p></p>
