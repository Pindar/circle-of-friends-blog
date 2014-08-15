---
layout: post
status: publish
published: true
title: ViewModel und das Problem mit den clientseitigen Anforderungsprüfungen
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
excerpt: 'Diesmal nehme ich Bezug auf meinen <a title="MVC-Nachfolger Model-View-ViewModel
  mit w3c-Standards &acirc;&euro;&rdquo; Ideen" href="http://www.pindarsign.de/webblog/?p=114"
  target="_self">letzten Blogeintrag</a>. Dort beschrieb ich das Model-View-ViewModel
  Pattern und insbesondere hob ich die besonderen Möglichkeiten der ViewModel
  Schicht heraus, die auch die Anforderungen an die Eingaben des Benutzers überprüfen
  sollte, und mit Hilfe der XForms-Technik kann dies zudem clientbasiert ablaufen.
  Nach einigen Überlegungen, wie das in einem praktischen Internet-Szenario
  aussehen könnte, bin ich nun der Meinung, dass die momentane Struktur
  bedingt, die Daten zweimalig zu prüfen: Zum einen clientseitig und
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
<p>Diesmal nehme ich Bezug auf meinen <a title="MVC-Nachfolger Model-View-ViewModel mit w3c-Standards &acirc;&euro;&rdquo; Ideen" href="http://www.pindarsign.de/webblog/?p=114" target="_self">letzten Blogeintrag</a>. Dort beschrieb ich das Model-View-ViewModel Pattern und insbesondere hob ich die besonderen Möglichkeiten der ViewModel Schicht heraus, die auch die Anforderungen an die Eingaben des Benutzers überprüfen sollte, und mit Hilfe der XForms-Technik kann dies zudem clientbasiert ablaufen. Nach einigen Überlegungen, wie das in einem praktischen Internet-Szenario aussehen könnte, bin ich nun der Meinung, dass die momentane Struktur bedingt, die Daten zweimalig zu prüfen: Zum einen clientseitig und zum anderen serverseitig.<a id="more"></a><a id="more-117"></a> Denn es wird an den Schnittstellen der Schichten nicht ausreichend sichergestellt, dass die an den Server übertragenen Daten wirklich den richtigen Anforderungen entsprechen. Auch fiel mir bisher keine Lösung ein, welcher man tatsächlich vertrauen könnte und sicherstellt, dass die erhaltenen Daten bereits überprüft sind. Eine clientseitige Signatur ist in diesem Fall nicht ausreichend, denn auch ein böswilliger Sender (Client) könnte seine Daten entsprechend signieren. Daher würde ein sogenannter "Point of Trust" im Clienten gebraucht, welchem unumstößliches Vertrauen beigemessen werden könnte. Ein Ablaufszenario könnte folgendermaßen beschrieben werden: ein Server signiert seine Anforderungen an die Benutereingaben und schickt diese gemeinsam mit der eben erstellten Signatur an den "Point of Trust" im Clienten. Dort würde die Prüfung der eingegebenen Daten gegen die Anforderungen stattfinden (zudem würde die Signatur geprüft und damit sichergestellt, dass die Anforderungen nicht verändert wurden) und anschließend würden die geprüften Daten zusammen mit der original-Signatur und der "Trust-Signatur" an den Server zurückgeschickt. Der Server könnte sich durch die zurückerhaltene original-Signatur sicher sein, dass die Daten gegen die gewünschten Anforderungen geprüft wurden und, dass eben dies auch sachgerecht von einem vertrauenswürdigen Programm durchgeführt wurde, da es vom "Point of Trust" ebenfalls signiert wurde.</p>
<p>Leider habe ich keine Ahnung, wie man einen solchen "Point of Trust" umsetzen sollte bzw. wie man sicherstellt, dass sich keine andere Software einfach an der "Point of Trust" Signatur bedient.</p>
<p>Ohne eines solchen oder ähnlichen Sicherheitsansatzes an den Schnittstellen zwischen Client und Server, können nur rudimentäre Prüfungen auf den Clienten abgewälzt werden. Wichtige Validierungen müssen leider zudem am Server durchgeführt werden, obwohl es wünschenswert wäre dort nur noch die wirkliche Logik ablaufen zu lassen. Bei einer sich in der freien Wildbahn befindlichen Anwendung, wird man jedoch gezwungen sein, sich auch gegen fingiert geprüfte Eingabedaten abzusichern.</p>
<p>Natürlich reduziert auch eine Anwendung, die eine Validierung doppelt durchführt die Client-Server Kommunikation vehement, aus dem Blickwinkel des Softwareengeniering betrachtet liegt mir die zweifache Validierung jedoch schwer im Magen. Zumindest sollte es möglich sein die deklarativ notierte Prüfung auch in andere Programmiersprachen, wie Java und PHP, zu integrieren, sodass zumindest eine zweifache Implementierung ausbleiben kann.</p>
<p>Wenn jemand Ideen dazu hat, wie man dieses "Problem" noch eleganter lösen könnte oder bereits kann, freue ich mich wie immer über alle Kommentare!</p>
