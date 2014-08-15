---
layout: post
status: publish
published: true
title: ViewModel und das Problem mit den clientseitigen Anforderungspr&Atilde;&frac14;fungen
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
excerpt: 'Diesmal nehme ich Bezug auf meinen <a title="MVC-Nachfolger Model-View-ViewModel
  mit w3c-Standards &acirc;&euro;&rdquo; Ideen" href="http:&#47;&#47;www.pindarsign.de&#47;webblog&#47;?p=114"
  target="_self">letzten Blogeintrag<&#47;a>. Dort beschrieb ich das Model-View-ViewModel
  Pattern und insbesondere hob ich die besonderen M&Atilde;&para;glichkeiten der ViewModel
  Schicht heraus, die auch die Anforderungen an die Eingaben des Benutzers &Atilde;&frac14;berpr&Atilde;&frac14;fen
  sollte, und mit Hilfe der XForms-Technik kann dies zudem clientbasiert ablaufen.
  Nach einigen &Atilde;&oelig;berlegungen, wie das in einem praktischen Internet-Szenario
  aussehen k&Atilde;&para;nnte, bin ich nun der Meinung, dass die momentane Struktur
  bedingt, die Daten zweimalig zu pr&Atilde;&frac14;fen: Zum einen clientseitig und
  zum anderen serverseitig.'
wordpress_id: 117
wordpress_url: http://www.pindarsign.de/webblog/?p=117
date: '2008-06-15 22:53:54 +0200'
date_gmt: '2008-06-15 20:53:54 +0200'
categories:
- code
tags:
- xforms
- mvvm
- viewmodel
- point of trust
comments: []
---
<p>Diesmal nehme ich Bezug auf meinen <a title="MVC-Nachfolger Model-View-ViewModel mit w3c-Standards &acirc;&euro;&rdquo; Ideen" href="http:&#47;&#47;www.pindarsign.de&#47;webblog&#47;?p=114" target="_self">letzten Blogeintrag<&#47;a>. Dort beschrieb ich das Model-View-ViewModel Pattern und insbesondere hob ich die besonderen M&Atilde;&para;glichkeiten der ViewModel Schicht heraus, die auch die Anforderungen an die Eingaben des Benutzers &Atilde;&frac14;berpr&Atilde;&frac14;fen sollte, und mit Hilfe der XForms-Technik kann dies zudem clientbasiert ablaufen. Nach einigen &Atilde;&oelig;berlegungen, wie das in einem praktischen Internet-Szenario aussehen k&Atilde;&para;nnte, bin ich nun der Meinung, dass die momentane Struktur bedingt, die Daten zweimalig zu pr&Atilde;&frac14;fen: Zum einen clientseitig und zum anderen serverseitig.<a id="more"></a><a id="more-117"></a> Denn es wird an den Schnittstellen der Schichten nicht ausreichend sichergestellt, dass die an den Server &Atilde;&frac14;bertragenen Daten wirklich den richtigen Anforderungen entsprechen. Auch fiel mir bisher keine L&Atilde;&para;sung ein, welcher man tats&Atilde;&curren;chlich vertrauen k&Atilde;&para;nnte und sicherstellt, dass die erhaltenen Daten bereits &Atilde;&frac14;berpr&Atilde;&frac14;ft sind. Eine clientseitige Signatur ist in diesem Fall nicht ausreichend, denn auch ein b&Atilde;&para;swilliger Sender (Client) k&Atilde;&para;nnte seine Daten entsprechend signieren. Daher w&Atilde;&frac14;rde ein sogenannter "Point of Trust" im Clienten gebraucht, welchem unumst&Atilde;&para;&Atilde;&Yuml;liches Vertrauen beigemessen werden k&Atilde;&para;nnte. Ein Ablaufszenario k&Atilde;&para;nnte folgenderma&Atilde;&Yuml;en beschrieben werden: ein Server signiert seine Anforderungen an die Benutereingaben und schickt diese gemeinsam mit der eben erstellten Signatur an den "Point of Trust" im Clienten. Dort w&Atilde;&frac14;rde die Pr&Atilde;&frac14;fung der eingegebenen Daten gegen die Anforderungen stattfinden (zudem w&Atilde;&frac14;rde die Signatur gepr&Atilde;&frac14;ft und damit sichergestellt, dass die Anforderungen nicht ver&Atilde;&curren;ndert wurden) und anschlie&Atilde;&Yuml;end w&Atilde;&frac14;rden die gepr&Atilde;&frac14;ften Daten zusammen mit der original-Signatur und der "Trust-Signatur" an den Server zur&Atilde;&frac14;ckgeschickt. Der Server k&Atilde;&para;nnte sich durch die zur&Atilde;&frac14;ckerhaltene original-Signatur sicher sein, dass die Daten gegen die gew&Atilde;&frac14;nschten Anforderungen gepr&Atilde;&frac14;ft wurden und, dass eben dies auch sachgerecht von einem vertrauensw&Atilde;&frac14;rdigen Programm durchgef&Atilde;&frac14;hrt wurde, da es vom "Point of Trust" ebenfalls signiert wurde.</p>
<p>Leider habe ich keine Ahnung, wie man einen solchen "Point of Trust" umsetzen sollte bzw. wie man sicherstellt, dass sich keine andere Software einfach an der "Point of Trust" Signatur bedient.</p>
<p>Ohne eines solchen oder &Atilde;&curren;hnlichen Sicherheitsansatzes an den Schnittstellen zwischen Client und Server, k&Atilde;&para;nnen nur rudiment&Atilde;&curren;re Pr&Atilde;&frac14;fungen auf den Clienten abgew&Atilde;&curren;lzt werden. Wichtige Validierungen m&Atilde;&frac14;ssen leider zudem am Server durchgef&Atilde;&frac14;hrt werden, obwohl es w&Atilde;&frac14;nschenswert w&Atilde;&curren;re dort nur noch die wirkliche Logik ablaufen zu lassen. Bei einer sich in der freien Wildbahn befindlichen Anwendung, wird man jedoch gezwungen sein, sich auch gegen fingiert gepr&Atilde;&frac14;fte Eingabedaten abzusichern.</p>
<p>Nat&Atilde;&frac14;rlich reduziert auch eine Anwendung, die eine Validierung doppelt durchf&Atilde;&frac14;hrt die Client-Server Kommunikation vehement, aus dem Blickwinkel des Softwareengeniering betrachtet liegt mir die zweifache Validierung jedoch schwer im Magen. Zumindest sollte es m&Atilde;&para;glich sein die deklarativ notierte Pr&Atilde;&frac14;fung auch in andere Programmiersprachen, wie Java und PHP, zu integrieren, sodass zumindest eine zweifache Implementierung ausbleiben kann.</p>
<p>Wenn jemand Ideen dazu hat, wie man dieses "Problem" noch eleganter l&Atilde;&para;sen k&Atilde;&para;nnte oder bereits kann, freue ich mich wie immer &Atilde;&frac14;ber alle Kommentare!</p>
