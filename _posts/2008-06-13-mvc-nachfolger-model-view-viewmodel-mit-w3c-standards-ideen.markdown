---
layout: post
status: publish
published: true
title: MVC-Nachfolger Model-View-ViewModel mit w3c-Standards -- Ideen
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
excerpt: 'Momentan beschäftige ich mich intensiv mit allem was irgendwo
  ein "X" im Namen hat. Von bekannten deklarativen Sprachen wie XHTML bis hin zu eher
  unbekannteren Dingen wie XUL, XAML, XSLT und XForms. Im Zuge dessen stieß
  ich auf das Model-View-ViewModel (M-V-VM) Pattern, das von John Gossman auf dessen
  Blog <a href="http://blogs.msdn.com/johngossman/default.aspx" target="_blank">"Thales
  from the Smart Client"</a> als erstes auftauchte und mittlerweile bereits auch
  in einigen <a href="http://www.thomasclaudiushuber.com/articles/ModelViewViewModelArticle.pdf"
  target="_blank">Zeitschriftenartikeln</a> von sich Reden machte. Auch lesenswert
  zu diesem Thema ist der Blogeintrag von Jens Peter Kleinau vom 20. September 2007:
  <a href="http://www.codecomplete.de/blogs/xamlblog/archive/2007/09/20/mvc-model-view-controller-reloaded-as-mvvm-model-view-viewmodel.aspx"
  target="_blank">"(MVC) Model-View-Controller &acirc;&euro;&ldquo; reloaded as (MVVM)
  Model-View-ViewModel"</a>. Alle diese Berichte beschreiben den Einsatz des M-V-VM
  Patterns nur im Hinblick auf Microsofts eigene XAML-Technik. Einen Artikel, der
  dieses interessante Pattern mit den vom w3 Konsortium standardisierten Techniken
  beschreibt, fand ich leider noch nicht, sodass ich diesen Ansatz nun hier einmal
  versuchen will.'
wordpress_id: 114
wordpress_url: http://www.pindarsign.de/webblog/?p=114
date: '2008-06-13 20:34:46 +0200'
date_gmt: '2008-06-13 18:34:46 +0200'
categories:
- code
tags:
- xml
- xaml
- xul
- xhtml
- xslt
- xforms
- css
- mvc
- mvvm
comments:
- id: 2320
  author: NimroT
  
  author_url: ''
  date: '2008-06-14 10:42:39 +0200'
  date_gmt: '2008-06-14 08:42:39 +0200'
  content: Klasse Artikel! Gefällt mir sehr gut.
---
<p>Momentan beschäftige ich mich intensiv mit allem was irgendwo ein "X" im Namen hat. Von bekannten deklarativen Sprachen wie XHTML bis hin zu eher unbekannteren Dingen wie XUL, XAML, XSLT und XForms. Im Zuge dessen stieß ich auf das Model-View-ViewModel (M-V-VM) Pattern, das von John Gossman auf dessen Blog <a href="http://blogs.msdn.com/johngossman/default.aspx" target="_blank">"Thales from the Smart Client"</a> als erstes auftauchte und mittlerweile bereits auch in einigen <a href="http://www.thomasclaudiushuber.com/articles/ModelViewViewModelArticle.pdf" target="_blank">Zeitschriftenartikeln</a> von sich Reden machte. Auch lesenswert zu diesem Thema ist der Blogeintrag von Jens Peter Kleinau vom 20. September 2007: <a href="http://www.codecomplete.de/blogs/xamlblog/archive/2007/09/20/mvc-model-view-controller-reloaded-as-mvvm-model-view-viewmodel.aspx" target="_blank">"(MVC) Model-View-Controller &acirc;&euro;&ldquo; reloaded as (MVVM) Model-View-ViewModel"</a>. Alle diese Berichte beschreiben den Einsatz des M-V-VM Patterns nur im Hinblick auf Microsofts eigene XAML-Technik. Einen Artikel, der dieses interessante Pattern mit den vom w3 Konsortium standardisierten Techniken beschreibt, fand ich leider noch nicht, sodass ich diesen Ansatz nun hier einmal versuchen will.<a id="more"></a><a id="more-114"></a></p>
<p>Zu aller erst eine kurze Erläuterung des Model-View-Controller "Nachfolgers". (Eine ausführliche Erläuterung findet sich in dem oben erwähnten Zeitschriftenartikel, was ich dem geneigten Leser bitten würde es bei Bedarf selbst zu lesen)</p>
<p>Das Model ist wie auch im MVC zur Datenkapselung verpflichtet. Es werden die Daten in "DataSets", XML-Dateien oder "Java-Beans" von einer Geschäftslogik, beispielsweise einer Java-Anwendung oder von PHP zur Verfügung gestellt und wiederum von dieser verarbeitet, was beispielsweise ein speichern der Daten in eine Datenbank zur Folge haben kann. Diese Geschäftslogik würde ich in einer Abwandlung des Patterns als eigene Schicht betrachten, etwas näher betrachte ich diesen punkt später.</p>
<p>Die View verantwortet die Darstellung der Daten und die ggf. dafür notwendige Umstrukturierung. Sie wird mittlerweile immer mehr von deklarativen Sprachen besetzt, wie XHTML, XAML, XUL. Dies hat die positive Eigenschaft, dass dafür immer mehr Programme existieren, die diese Strukturierung vereinfachen, wie "Frontpage", Blend für XAML usw. . Dadurch kann auch ein Designer mit wenig Programmierkenntnissen diese Arbeit erledigen.</p>
<p>Das "neue" ViewModel ist aus der Microsoft XAML Sicht vom Entwickler beispielsweise in C# Code zu implementieren. Es dient zur View-Logik-Steuerung und gibt die Daten immer an den richtigen Ort beziehungsweise prüft die eingegebenen Daten auf deren Gültigkeit. Zudem hat es Kenntnis über die View, was eine nähere Ausrichtung zur View ist, wie beim Controller.</p>
<p>Ein weiterer Bereich, ich nenne ihn der Einfachheit halber "Logik" verbindet dann noch die View und das Model mit externen Quellen wie einer Datenbank und prüft Requirements, die von der etwas einfacheren ViewModel-Schicht nicht geprüft werden können, wie <span style="color: #8b0000;">referezielle Integrität. Hauptgrund für diese zusätzliche Schicht ist der Aufbau der w3-Standards. Wie im folgenden erläutert, sind View, ViewModel und zum Teil auch das Model Clientbasiert umzusetzen. Um die Client-Server-Aufteilung noch deutlicher machen zu können, entschied ich mich für eine Logik-Schicht, die klar auf Serverseite anzusiedeln ist.*</span></p>
<p>Nun aber aus der Sichtweise mit w3-Standards:<br />
Den Entscheidenden Unterschied macht hier das ViewModel. Denn im Gegensatz zur XAML-Sicht, der diesen Bereich in einer Programmiersprache &Atilde;&nbsp; la C# umzusetzt, wird hier das ViewModel durch die XForms-Technik bereitgestellt <span style="color: #800000;">(also auch vollständig Clientseitig)</span>*. Diese Technik ist vollständig deklarativ aufgebaut und kann in allen XML-Dateien als Modul integriert werden. XForms selbst ist eine Weiterentwicklung des Formulars in HTML, bietet aber weit mehr als diese verstaubte Technik. XForms vermag es eingegebene Daten gegen (auch selbst erstellte) Datentypen zu validieren. Auch Event-Handling und Actions können damit deklarativ beschrieben werden. AJAX wird beinahe überflüssig. Was hat das nun aber mit dem Pattern zu tun? Nun, bisher mussten gerade solche Prüfroutinen entweder in den Controller-Teil des Programms aufgenommen werden, oder alternativ durch Skriptings in den View-Bereich integriert werden. Die Skripting-Variante hat aber den entscheidenden Nachteil, das die Ausführung von Skripten in Sicherheitsrelevanten Umgebungen oft deaktiviert sind und so mehr ViewModel-Logik in die Controller-Schicht integriert werden müssen, was zu immer sehr aufwendigen Validierungen im Code führte und diesen unnötig aufblähte. XAML macht es hier leider auch nicht viel besser, da auch in der .NET Umgebung diese Prüfungen von C# Code durchgeführt wird, welcher sich nach Definition aber bereits in der ViewModel-Schicht befindet. Eine Klare Trennung des Logik-Bereichs und stumpfsinnigen Eingabeüberprüfungen ist damit für meine Begriffe jedoch nicht ausreichend gegeben.</p>
<p>Durch XForms, welches zudem die Eigenschaft besitzt Formularfelder aus einer Instance-Datei vorauszufüllen und damit in sich bereits das MVVM-Pattern realisiert, wird eine klare Trennung möglich. XForms ist selbst in eine Art View (input, output-Felder, label-Tags usw.), ViewModel (Action-Handling, Requirements, Data-Binding) und Model (instance-Data) aufgeteilt. Wenn man diese Basistechnik noch mit XHTML ganiert, welche die Visuelle-Struktur festlegt, etwas CSS 3 dazu gibt, welches sich um das Styling kümmert, XSLT, um die XML-Daten aus dem Model in das XHTML zu integrieren, nimmt und eine Programmiersprache wie Java oder PHP die die XML-Daten von Model verarbeitet bzw. aus der Datenbank erstellt und somit die Logik-Schicht repräsentiert, dann sollte man eine saubere Trennung zwischen allen Schichten erreichen können.</p>
<p>Damit man sich all diese Zusammenhänge, die textuell doch etwas schwer erläuterbar sind, etwas besser vorstellen kann, betrachte man folgende Abbildung:</p>
<p><a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/06/model-view-viewmodel.png"><img class="alignnone size-medium wp-image-116" title="model-view-viewmodel Grafik" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/06/model-view-viewmodel-300x169.png" alt="" width="300" height="169" /></a></p>
<p>In den nächsten Tagen werde ich versuchen immer wieder Artikel zu Themen mit einem "X" im Namen zu veröffentlichen. Bei Anregungen zu meiner Pattern-Überlegung freue ich mich über alle Kommentare! Und nun wünsche ich allen ein schönes Wochenende.</p>
<p>*rot markiert sind erneuerte Textstellen.</p>
