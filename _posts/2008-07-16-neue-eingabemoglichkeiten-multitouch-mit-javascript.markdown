---
layout: post
status: publish
published: true
title: Neue Eingabem&Atilde;&para;glichkeiten... Multitouch mit JavaScript
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
wordpress_id: 175
wordpress_url: http://www.pindarsign.de/webblog/?p=175
date: '2008-07-16 14:06:28 +0200'
date_gmt: '2008-07-16 12:06:28 +0200'
categories:
- Technik
- web 2.0
tags:
- css
- multitouch
- javascript
- webkit
comments:
- id: 2899
  author: Strahler
  
  author_url: ''
  date: '2008-07-16 15:12:11 +0200'
  date_gmt: '2008-07-16 13:12:11 +0200'
  content: ":-) Oder einfach zweite Maus anschlie&Atilde;&Yuml;en und dann geht's
    mit MPX (F&Atilde;&frac14;r den XServer) ab: \r\nKann man jetzt schon installieren
    und is standardm&Atilde;&curren;&Atilde;&Yuml;ig in der n&Atilde;&curren;chstne
    X-Version drin. ;)\r\n\r\nhttp:&#47;&#47;www.youtube.com&#47;watch?v=0MUOn_nJmRA\r\n\r\nhttp:&#47;&#47;www.youtube.com&#47;watch?v=olWjnfBoY8E&amp;feature=related\r\n\r\nGru&Atilde;&Yuml;\r\nStrahler
    ;)"
- id: 2900
  author: NimroT
  
  author_url: ''
  date: '2008-07-16 16:13:31 +0200'
  date_gmt: '2008-07-16 14:13:31 +0200'
  content: ich finde die Technik im Browser irgendwie ein wenig fehl am Platze....
    aber vielleicht diffundiert das ja noch weiter runter...
- id: 2901
  author: Pindar
  
  author_url: http://www.pindarsign.de
  date: '2008-07-16 17:14:11 +0200'
  date_gmt: '2008-07-16 15:14:11 +0200'
  content: Hallo NimroT. Wieso findest Du diese Technik im Browser unpassend? Und
    was meinst Du mit "aber vielleicht diffundiert das ja noch weiter runter&acirc;&euro;&brvbar;".
    Ich versteh Dich leider nicht.
- id: 2902
  author: NimroT
  
  author_url: ''
  date: '2008-07-16 20:36:57 +0200'
  date_gmt: '2008-07-16 18:36:57 +0200'
  content: "naja, Multitouch ist ja eine mehr oder weniger neue Eingabetechnik. Ich
    finde, dass sowas nicht in den Browser geh&Atilde;&para;rt, sondern direkt ins
    Betriebssystem (oder halt in den XServer ;-)), damit man nicht nur in einem Programm
    davon profitieren kann. Aber wie schon gesagt: das ist nur meine Meinung, die
    nicht auf irgendwelchem, hochgeistigem Hintergrundwissen basiert.\r\n\r\nEinigerma&Atilde;&Yuml;en
    verst&Atilde;&curren;ndlich geworden, was ich meine?"
- id: 2903
  author: Pindar
  
  author_url: http://www.pindarsign.de
  date: '2008-07-16 22:32:29 +0200'
  date_gmt: '2008-07-16 20:32:29 +0200'
  content: "Achso. Dann ist die &Atilde;&oelig;berschrift wohl falsch interpretierbar.
    Die Multitouch-Technik wird nat&Atilde;&frac14;rlich vom Treiber der Hardware
    dem ganzen System bereit gestellt. Genauso wie eben auch eine Maus nicht nur im
    Browser funktioniert. Das tolle und neue ist also nur, dass man nun auch diese
    Technik im Browser nutzen kann. Bisher gibt es Event-Listener f&Atilde;&frac14;r
    Mausklicks (click) oder ob die Maus &Atilde;&frac14;ber einem Feld ist (mouseover).
    Nun ist es auch m&Atilde;&para;glich die \"Touchs\" zu erkennen. Ist doch wunderbar!
    Ich kann mir einige speziell f&Atilde;&frac14;r das iPhone (iPod Touch) entwickelte
    Webseiten vorstellen, die diese Eingabem&Atilde;&para;glichkeiten nutzbringend
    umsetzen. \r\nAbschlie&Atilde;&Yuml;end noch etwas anders und direkt gesagt: Du
    w&Atilde;&frac14;rdest doch sicher auch nicht sagen, dass die Maus anzusteuern
    im Browser nichts verloren hat."
- id: 2904
  author: NimroT
  
  author_url: ''
  date: '2008-07-17 07:06:45 +0200'
  date_gmt: '2008-07-17 05:06:45 +0200'
  content: 'naja, wenn NUR der browser die maus verwenden k&Atilde;&para;nnte w&Atilde;&frac14;rde
    ich schon sagen: das hat da nichts verloren.'
- id: 2905
  author: Pindar
  
  author_url: http://www.pindarsign.de
  date: '2008-07-17 07:55:27 +0200'
  date_gmt: '2008-07-17 05:55:27 +0200'
  content: "Ok, das w&Atilde;&curren;re dann wohl auch sinnlos :) \r\nAber jetzt verstehen
    wir uns."
---
<p>Mit der neuesten Webkit-Version von Safari kann man Multitouch auch mit dem normalen Desktop simulieren. Was sich dabei f&Atilde;&frac14;r M&Atilde;&para;glichkeiten bieten, k&Atilde;&para;nnt ihr euch in diesem kleinen Video anschauen:<br />
<object classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" width="481" height="338" codebase="http:&#47;&#47;download.macromedia.com&#47;pub&#47;shockwave&#47;cabs&#47;flash&#47;swflash.cab#version=6,0,40,0" data="&#47;webblog&#47;wp-content&#47;uploads&#47;2008&#47;07&#47;screen.swf"><br />
<embed type="application&#47;x-shockwave-flash" width="481" height="338" src="&#47;webblog&#47;wp-content&#47;uploads&#47;2008&#47;07&#47;screen.swf"><&#47;embed><&#47;object><br />
Das Prinzip ist einfach. Man klickt auf ein Bild. Dieser Punkt ist dann der Referenzpunkt. Beim zweiten Klick kann man so das Bild drehen, vergr&Atilde;&para;&Atilde;&Yuml;ern usw. Und alles das mit einem herk&Atilde;&para;mmlichen Browser. Ich freue mich schon auf die Einf&Atilde;&frac14;hrung.</p>
<p>[youtube -XKb8We_uzg]<br />
Weblinks:</p>
<ul>
<li><a href="http:&#47;&#47;tlrobinson.net&#47;blog&#47;?p=42" target="_blank">http:&#47;&#47;tlrobinson.net&#47;blog&#47;?p=42<&#47;a><&#47;li><br />
<&#47;ul></p>
