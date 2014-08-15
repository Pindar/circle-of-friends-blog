---
layout: post
status: publish
published: true
title: Lexikon in Leopard erweitern (Teil 2)
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
wordpress_id: 57
wordpress_url: http://www.pindarsign.de/webblog/?p=57
date: '2008-02-14 18:38:47 +0100'
date_gmt: '2008-02-14 17:38:47 +0100'
categories:
- Allgemein
- Technik
- Tools
- Apple
tags:
- apple
- lexikon
- programme
- plugin
comments:
- id: 223
  author: Martin Michel
  
  author_url: http://www.joyofscripting.com
  date: '2008-02-14 19:00:32 +0100'
  date_gmt: '2008-02-14 18:00:32 +0100'
  content: "Vielen Dank für dieses praktische Dictionary-Plugin! Endlich
    mal was in unserer Landessprache *g* Funktioniert hier einwandfrei und gut, bis
    auf die noch nicht korrekt angezeigten Umlaute.\r\n\r\nEs ist wirklich schade,
    daß es leider immer noch recht wenige Plugins für
    das Dictionary gibt, ich finde die nämlich äußerst
    nett. Und die Herstellung ist ja gar nicht so schwer :-)\r\n\r\nNochmals danke!
    Und beste Grüße in den Süden aus Ostwestfalen!"
- id: 229
  author: Tekl
  
  author_url: http://www.tekl.de
  date: '2008-03-14 06:35:56 +0100'
  date_gmt: '2008-03-14 05:35:56 +0100'
  content: "Hallo,\r\n\r\nda hat sich doch tatsächlich schon jemand
    die Mühe gemacht, OpenThesaurus für's Lexikon aufzubereiten.
    Naja, besser doppelt als gar nicht. :-)\r\n\r\nBei meiner Variante gibt's noch
    ein paar Treffer mehr pro Suchbegriff (z. B. 'Aktie'). \r\n\r\nhttp://www.tekl.de\r\n\r\nTekl"
- id: 2561
  author: Freak
  
  author_url: ''
  date: '2008-06-25 18:56:06 +0200'
  date_gmt: '2008-06-25 16:56:06 +0200'
  content: und was ist mit 10.4? :(
- id: 2564
  author: Pindar
  
  author_url: http://www.pindarsign.de
  date: '2008-06-26 09:30:47 +0200'
  date_gmt: '2008-06-26 07:30:47 +0200'
  content: "@Freak: OS 10.4 hat eine andere Datenstruktur für das Lexikon.
    Leider ist es deshalb wesentlich umständlicher Erweiterungen für
    10.4 zu schreiben. Tut mir Leid."
- id: 4139
  author: dave
  
  author_url: ''
  date: '2008-08-17 10:58:17 +0200'
  date_gmt: '2008-08-17 08:58:17 +0200'
  content: "Herzlichen dank! nach sowas habe ich schon lange gesucht...\r\neinfach
    praktisch...\r\n\r\ngruss\r\ndave"
- id: 15528
  author: Nomen
  
  author_url: ''
  date: '2008-10-14 00:18:22 +0200'
  date_gmt: '2008-10-13 22:18:22 +0200'
  content: 'Da gibt es nur eins zu sagen: DANKE !!!'
- id: 37925
  author: Update OpenThesaurus fürs Apple Lexikon at .pindarsign|blog
  
  author_url: http://www.pindarsign.de/webblog/?p=644
  date: '2008-12-06 18:27:27 +0100'
  date_gmt: '2008-12-06 17:27:27 +0100'
  content: "[...] von Heute findet sich ab jetzt auf dem Blog. Die alte Download-Datei
    wurde ersetzt, sodass auch vom alten Blogeintrag die neue Version heruntergeladen
    werden [...]"
---
<p>(Update 13. August 2009) Eine neue Version steht zum Download bereit. (Datenbasis: anfang August).</p>
<p>(Update 6. Dezember 2008) Eine neue Version steht zum Download bereit. (Datenbasis: 1076 KB, generiert 2008-12-06 00:37).</p>
<p>Neues Feature: Jetzt ist ein Online-Link direkt auf die jeweilige Seite von OpenThesaurus integriert.</p>
<p><em>(Update 2) Eben habe ich eine ganz aktuelle Version hochgeladen, darin sind alle Umlautprobleme beseitigt und noch ein paar kleine Korrekturen gemacht. Ich möchte mich, jetzt nach Vollendung des Projektes, noch bei Daniel Naber, dem Initiator von openthesaurus.de, bedanken für die freundliche Bereitstellung der Datenbasis und der Hilfestellung, mit dieser Datenbank auch umgehen zu können.</em><br />
<em>Sobald wieder eine neue Datenbasis von openthesaurus herausgegeben wird, werde ich hier eine aktualisierte Version zur Verfügung stellen. Das hier angebotene Plugin greift nämlich nicht auf den Webinhalt von openthesaurus zu, sondern beinhaltet alle Daten in sich - funktioniert also auch offline. Nun wünsche ich noch allen ein schönes Wochenende!</em></p>
<p><img src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/02/screenshot.gif" alt="Aktuelle Ansicht" width="443" height="282" /></p>
<p>Heute habe ich mich hingesetzt und mein erstes Apple-Plugin geschrieben. Ihr findet nun das gesamte Wissen von www.openthesaurus.de als Plugin. Noch ist nicht alles perfekt (<span style="text-decoration: line-through;">Umlaute funktionieren noch nicht</span> etc.), aber für die meisten Worte funktioniert es schon ganz prächtig, daher möchte ich es euch nicht vorenthalten.</p>
<p>Die Installationsanleitung habe ich von <a href="http://joyofscripting.com/wp/?p=109" target="_blank">http://joyofscripting.com/wp/?p=109</a> übernommen:</p>
<blockquote><p><span style="text-decoration: underline;">Installation:</span><br />
Zunächst muß die ZIP-Datei natürlich heruntergeladen und entpackt werden.<br />
Danach wird das Wörterbuchpaket einfach in folgendes Verzeichnis kopiert (<em>deinname</em> muß selbstredend mit Deinem Mac OS X-Kurznamen ersetzt werden):</p>
<p class="codesnip-container"></p></p>
<p class="codesnip">/Benutzer/deinname/Library/Dictionaries/</p></p>
<p>Sollte der Ordner &acirc;&euro;&oelig;Dictionaries&acirc;&euro; noch nicht existieren, dann lege ihn freundlicherweise an.</p>
<p>Jetzt nur noch das Lexikon in Leopard starten/neustarten und schon kann die Suche nach Postleitzahlen und Vorwahlen deutscher Städte losgehen.</p>
<p>Ein kleiner Tip: Wenn man in Mac OS X gleichzeitig Steuerung + Apfeltaste + D gedrückt hält und dann mit dem Mauszeiger über ein Wort in einem Dokument oder einer Webseite fährt, erscheinen dazu in einem schwebenden Fenster die passenden Einträge aus dem Lexikon</blockquote><br />
Ich wünsche allen viel Freude damit und <span style="text-decoration: line-through;">demnächst kommt dann auch die vollfunktionierende Version online</span>.</p>
<p>[<a title="OpenThesaurus-Lexikon-Erweiterung" href="/webblog/wp-content/uploads/2008/01/OpenThesaurus.dictionary.zip">Download</a>]</p>
