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
excerpt: 'Momentan besch&Atilde;&curren;ftige ich mich intensiv mit allem was irgendwo
  ein "X" im Namen hat. Von bekannten deklarativen Sprachen wie XHTML bis hin zu eher
  unbekannteren Dingen wie XUL, XAML, XSLT und XForms. Im Zuge dessen stie&Atilde;&Yuml;
  ich auf das Model-View-ViewModel (M-V-VM) Pattern, das von John Gossman auf dessen
  Blog <a href="http:&#47;&#47;blogs.msdn.com&#47;johngossman&#47;default.aspx" target="_blank">"Thales
  from the Smart Client"<&#47;a> als erstes auftauchte und mittlerweile bereits auch
  in einigen <a href="http:&#47;&#47;www.thomasclaudiushuber.com&#47;articles&#47;ModelViewViewModelArticle.pdf"
  target="_blank">Zeitschriftenartikeln<&#47;a> von sich Reden machte. Auch lesenswert
  zu diesem Thema ist der Blogeintrag von Jens Peter Kleinau vom 20. September 2007:
  <a href="http:&#47;&#47;www.codecomplete.de&#47;blogs&#47;xamlblog&#47;archive&#47;2007&#47;09&#47;20&#47;mvc-model-view-controller-reloaded-as-mvvm-model-view-viewmodel.aspx"
  target="_blank">"(MVC) Model-View-Controller &acirc;&euro;&ldquo; reloaded as (MVVM)
  Model-View-ViewModel"<&#47;a>. Alle diese Berichte beschreiben den Einsatz des M-V-VM
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
  content: Klasse Artikel! Gef&Atilde;&curren;llt mir sehr gut.
---
<p>Momentan besch&Atilde;&curren;ftige ich mich intensiv mit allem was irgendwo ein "X" im Namen hat. Von bekannten deklarativen Sprachen wie XHTML bis hin zu eher unbekannteren Dingen wie XUL, XAML, XSLT und XForms. Im Zuge dessen stie&Atilde;&Yuml; ich auf das Model-View-ViewModel (M-V-VM) Pattern, das von John Gossman auf dessen Blog <a href="http:&#47;&#47;blogs.msdn.com&#47;johngossman&#47;default.aspx" target="_blank">"Thales from the Smart Client"<&#47;a> als erstes auftauchte und mittlerweile bereits auch in einigen <a href="http:&#47;&#47;www.thomasclaudiushuber.com&#47;articles&#47;ModelViewViewModelArticle.pdf" target="_blank">Zeitschriftenartikeln<&#47;a> von sich Reden machte. Auch lesenswert zu diesem Thema ist der Blogeintrag von Jens Peter Kleinau vom 20. September 2007: <a href="http:&#47;&#47;www.codecomplete.de&#47;blogs&#47;xamlblog&#47;archive&#47;2007&#47;09&#47;20&#47;mvc-model-view-controller-reloaded-as-mvvm-model-view-viewmodel.aspx" target="_blank">"(MVC) Model-View-Controller &acirc;&euro;&ldquo; reloaded as (MVVM) Model-View-ViewModel"<&#47;a>. Alle diese Berichte beschreiben den Einsatz des M-V-VM Patterns nur im Hinblick auf Microsofts eigene XAML-Technik. Einen Artikel, der dieses interessante Pattern mit den vom w3 Konsortium standardisierten Techniken beschreibt, fand ich leider noch nicht, sodass ich diesen Ansatz nun hier einmal versuchen will.<a id="more"></a><a id="more-114"></a></p>
<p>Zu aller erst eine kurze Erl&Atilde;&curren;uterung des Model-View-Controller "Nachfolgers". (Eine ausf&Atilde;&frac14;hrliche Erl&Atilde;&curren;uterung findet sich in dem oben erw&Atilde;&curren;hnten Zeitschriftenartikel, was ich dem geneigten Leser bitten w&Atilde;&frac14;rde es bei Bedarf selbst zu lesen)</p>
<p>Das Model ist wie auch im MVC zur Datenkapselung verpflichtet. Es werden die Daten in "DataSets", XML-Dateien oder "Java-Beans" von einer Gesch&Atilde;&curren;ftslogik, beispielsweise einer Java-Anwendung oder von PHP zur Verf&Atilde;&frac14;gung gestellt und wiederum von dieser verarbeitet, was beispielsweise ein speichern der Daten in eine Datenbank zur Folge haben kann. Diese Gesch&Atilde;&curren;ftslogik w&Atilde;&frac14;rde ich in einer Abwandlung des Patterns als eigene Schicht betrachten, etwas n&Atilde;&curren;her betrachte ich diesen punkt sp&Atilde;&curren;ter.</p>
<p>Die View verantwortet die Darstellung der Daten und die ggf. daf&Atilde;&frac14;r notwendige Umstrukturierung. Sie wird mittlerweile immer mehr von deklarativen Sprachen besetzt, wie XHTML, XAML, XUL. Dies hat die positive Eigenschaft, dass daf&Atilde;&frac14;r immer mehr Programme existieren, die diese Strukturierung vereinfachen, wie "Frontpage", Blend f&Atilde;&frac14;r XAML usw. . Dadurch kann auch ein Designer mit wenig Programmierkenntnissen diese Arbeit erledigen.</p>
<p>Das "neue" ViewModel ist aus der Microsoft XAML Sicht vom Entwickler beispielsweise in C# Code zu implementieren. Es dient zur View-Logik-Steuerung und gibt die Daten immer an den richtigen Ort beziehungsweise pr&Atilde;&frac14;ft die eingegebenen Daten auf deren G&Atilde;&frac14;ltigkeit. Zudem hat es Kenntnis &Atilde;&frac14;ber die View, was eine n&Atilde;&curren;here Ausrichtung zur View ist, wie beim Controller.</p>
<p>Ein weiterer Bereich, ich nenne ihn der Einfachheit halber "Logik" verbindet dann noch die View und das Model mit externen Quellen wie einer Datenbank und pr&Atilde;&frac14;ft Requirements, die von der etwas einfacheren ViewModel-Schicht nicht gepr&Atilde;&frac14;ft werden k&Atilde;&para;nnen, wie <span style="color: #8b0000;">referezielle Integrit&Atilde;&curren;t. Hauptgrund f&Atilde;&frac14;r diese zus&Atilde;&curren;tzliche Schicht ist der Aufbau der w3-Standards. Wie im folgenden erl&Atilde;&curren;utert, sind View, ViewModel und zum Teil auch das Model Clientbasiert umzusetzen. Um die Client-Server-Aufteilung noch deutlicher machen zu k&Atilde;&para;nnen, entschied ich mich f&Atilde;&frac14;r eine Logik-Schicht, die klar auf Serverseite anzusiedeln ist.*<&#47;span></p>
<p>Nun aber aus der Sichtweise mit w3-Standards:<br />
Den Entscheidenden Unterschied macht hier das ViewModel. Denn im Gegensatz zur XAML-Sicht, der diesen Bereich in einer Programmiersprache &Atilde;&nbsp; la C# umzusetzt, wird hier das ViewModel durch die XForms-Technik bereitgestellt <span style="color: #800000;">(also auch vollst&Atilde;&curren;ndig Clientseitig)<&#47;span>*. Diese Technik ist vollst&Atilde;&curren;ndig deklarativ aufgebaut und kann in allen XML-Dateien als Modul integriert werden. XForms selbst ist eine Weiterentwicklung des Formulars in HTML, bietet aber weit mehr als diese verstaubte Technik. XForms vermag es eingegebene Daten gegen (auch selbst erstellte) Datentypen zu validieren. Auch Event-Handling und Actions k&Atilde;&para;nnen damit deklarativ beschrieben werden. AJAX wird beinahe &Atilde;&frac14;berfl&Atilde;&frac14;ssig. Was hat das nun aber mit dem Pattern zu tun? Nun, bisher mussten gerade solche Pr&Atilde;&frac14;froutinen entweder in den Controller-Teil des Programms aufgenommen werden, oder alternativ durch Skriptings in den View-Bereich integriert werden. Die Skripting-Variante hat aber den entscheidenden Nachteil, das die Ausf&Atilde;&frac14;hrung von Skripten in Sicherheitsrelevanten Umgebungen oft deaktiviert sind und so mehr ViewModel-Logik in die Controller-Schicht integriert werden m&Atilde;&frac14;ssen, was zu immer sehr aufwendigen Validierungen im Code f&Atilde;&frac14;hrte und diesen unn&Atilde;&para;tig aufbl&Atilde;&curren;hte. XAML macht es hier leider auch nicht viel besser, da auch in der .NET Umgebung diese Pr&Atilde;&frac14;fungen von C# Code durchgef&Atilde;&frac14;hrt wird, welcher sich nach Definition aber bereits in der ViewModel-Schicht befindet. Eine Klare Trennung des Logik-Bereichs und stumpfsinnigen Eingabe&Atilde;&frac14;berpr&Atilde;&frac14;fungen ist damit f&Atilde;&frac14;r meine Begriffe jedoch nicht ausreichend gegeben.</p>
<p>Durch XForms, welches zudem die Eigenschaft besitzt Formularfelder aus einer Instance-Datei vorauszuf&Atilde;&frac14;llen und damit in sich bereits das MVVM-Pattern realisiert, wird eine klare Trennung m&Atilde;&para;glich. XForms ist selbst in eine Art View (input, output-Felder, label-Tags usw.), ViewModel (Action-Handling, Requirements, Data-Binding) und Model (instance-Data) aufgeteilt. Wenn man diese Basistechnik noch mit XHTML ganiert, welche die Visuelle-Struktur festlegt, etwas CSS 3 dazu gibt, welches sich um das Styling k&Atilde;&frac14;mmert, XSLT, um die XML-Daten aus dem Model in das XHTML zu integrieren, nimmt und eine Programmiersprache wie Java oder PHP die die XML-Daten von Model verarbeitet bzw. aus der Datenbank erstellt und somit die Logik-Schicht repr&Atilde;&curren;sentiert, dann sollte man eine saubere Trennung zwischen allen Schichten erreichen k&Atilde;&para;nnen.</p>
<p>Damit man sich all diese Zusammenh&Atilde;&curren;nge, die textuell doch etwas schwer erl&Atilde;&curren;uterbar sind, etwas besser vorstellen kann, betrachte man folgende Abbildung:</p>
<p><a href="http:&#47;&#47;www.pindarsign.de&#47;webblog&#47;wp-content&#47;uploads&#47;2008&#47;06&#47;model-view-viewmodel.png"><img class="alignnone size-medium wp-image-116" title="model-view-viewmodel Grafik" src="http:&#47;&#47;www.pindarsign.de&#47;webblog&#47;wp-content&#47;uploads&#47;2008&#47;06&#47;model-view-viewmodel-300x169.png" alt="" width="300" height="169" &#47;><&#47;a></p>
<p>In den n&Atilde;&curren;chsten Tagen werde ich versuchen immer wieder Artikel zu Themen mit einem "X" im Namen zu ver&Atilde;&para;ffentlichen. Bei Anregungen zu meiner Pattern-&Atilde;&oelig;berlegung freue ich mich &Atilde;&frac14;ber alle Kommentare! Und nun w&Atilde;&frac14;nsche ich allen ein sch&Atilde;&para;nes Wochenende.</p>
<p>*rot markiert sind erneuerte Textstellen.</p>
