---
layout: post
status: publish
published: true
title: Vorstellungsreihe von deklarativen UI-Sprachen (2) XAML
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
excerpt: W&Atilde;&curren;hrend den Vorbereitungen auf Windows Vista wurde auch an
  einer neuen Sprache gearbeitet, die es Entwicklern einfacher machen sollte, Anwendungen
  grafisch ansprechender schreiben zu k&Atilde;&para;nnen und das mit geringerem Aufwand.
  Microsoft arbeitete daher an "Avalon" f&Atilde;&frac14;r Windows "Longhorn", aus
  welchem die "Windows Presentation Foundation" (WPF) hervorging. Diese Entwicklungen
  brachte die deklarative Sprache XAML hervor, mit Hilfe derer man Oberfl&Atilde;&curren;chen
  via einer XML-Datei beschreiben kann, &Atilde;&curren;hnlich XHTML zusammen mit
  SMIL. Microsofts Silverlight ist eine Teilmenge von WPF. F&Atilde;&frac14;r Silverlightche
  gibt es Laufzeitumgebungen als Plug-In auch f&Atilde;&frac14;r nicht Microsoft-Produkte,
  wie dem Firefox und Safari. Des weiteren wird Silverlight auch auf weiteren Plattformen,
  wie Apples Macintosh und Linux (hier unter dem Namen "Moonlight"), unterst&Atilde;&frac14;tzt.
  Es Positioniert sich folglich gegen Adobe AIR.
wordpress_id: 122
wordpress_url: http://www.pindarsign.de/webblog/?p=122
date: '2008-06-19 18:04:16 +0200'
date_gmt: '2008-06-19 16:04:16 +0200'
categories:
- Rich Internet Application
tags:
- xaml
- xforms
- silverlight
- smil
- ui
comments:
- id: 2324
  author: NimroT
  
  author_url: ''
  date: '2008-06-20 16:13:05 +0200'
  date_gmt: '2008-06-20 14:13:05 +0200'
  content: Ich habe vor kurzem gelesen, dass das Framework von Apple (noch?) gar nicht
    &Atilde;&para;ffentlich dokumentiert ist, und alle bisherigen tiefer gehenden
    Informationen aus einem OpenSource-Projekt stammen, auf dem Apple aufbaut. Stimmt
    das soweit?
---
<p>W&Atilde;&curren;hrend den Vorbereitungen auf Windows Vista wurde auch an einer neuen Sprache gearbeitet, die es Entwicklern einfacher machen sollte, Anwendungen grafisch ansprechender schreiben zu k&Atilde;&para;nnen und das mit geringerem Aufwand. Microsoft arbeitete daher an "Avalon" f&Atilde;&frac14;r Windows "Longhorn", aus welchem die "Windows Presentation Foundation" (WPF) hervorging. Diese Entwicklungen brachte die deklarative Sprache XAML hervor, mit Hilfe derer man Oberfl&Atilde;&curren;chen via einer XML-Datei beschreiben kann, &Atilde;&curren;hnlich XHTML zusammen mit SMIL. Microsofts Silverlight ist eine Teilmenge von WPF. F&Atilde;&frac14;r Silverlightche gibt es Laufzeitumgebungen als Plug-In auch f&Atilde;&frac14;r nicht Microsoft-Produkte, wie dem Firefox und Safari. Des weiteren wird Silverlight auch auf weiteren Plattformen, wie Apples Macintosh und Linux (hier unter dem Namen "Moonlight"), unterst&Atilde;&frac14;tzt. Es Positioniert sich folglich gegen Adobe AIR.<a id="more"></a><a id="more-122"></a></p>
<h2>Aufbau von XAML<&#47;h2><br />
XAML selbst ist, wie bereits erw&Atilde;&curren;hnt eine Sprache, die deklarativ ein User Interface (UI) beschreibt. Der Mehrwert gegen&Atilde;&frac14;ber dem offenen XHTML-Standard bietet die Sprache in der Animationsf&Atilde;&curren;higkeit von Objekten. Da Microsoft auch an der Entwicklung von SMIL, dem offenen, ebenfalls auf XML basierenden W3-Standard, beteiligt war und selbst SMIL 2.0 fast vollst&Atilde;&curren;ndig seit Version 5 des Internet Explorers implementierte, verwundert eine gewisse syntaktische &Atilde;&bdquo;hnlichkeit der beiden Sprachen nicht. Viel mehr verwundert jedoch, dass Microsoft &Atilde;&frac14;berhaupt an einem neuen Standard arbeitete und nicht den bereits existierenden offenen w3 Standard einfach weiterentwickelt wiederverwendet hat. Auch wurden in einigen <a href="http:&#47;&#47;www.simplegeek.com&#47;PermaLink.aspx&#47;b7e02709-0112-4977-9b73-1aa9d471a570" target="_blank">Blog-Beitr&Atilde;&curren;gen<&#47;a> Probleme diskutiert, welche <a href="http:&#47;&#47;www.w3.org&#47;1999&#47;08&#47;WD-smil-boston-19990803&#47;Integrate&#47;Time-Integrate#CSSFramework" target="_blank">bereits Jahre zuvor<&#47;a> ebenfalls im SMIL-Lager (unter sehr starker Microsoft-Beteiligung) diskutiert wurden, was einer entsprechende "s&Atilde;&frac14;ffisanz" nicht abtr&Atilde;&curren;glich wird.</p>
<p>Nun aber ein Beispiel-Code einer typischen XAML-Anwendung (Von <a href="http:&#47;&#47;www.silverlight.net&#47;quickstarts&#47;silverlight10&#47;drawing.aspx" target="_blank">Silverlight Quickstart<&#47;a> entnommen):</p>
<pre><span class="code-blue"><<&#47;span><span class="code-brown">Canvas<&#47;span><br />
    <span class="code-red">xmlns<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"http:&#47;&#47;schemas.microsoft.com&#47;client&#47;2007"<&#47;span><br />
    <span class="code-red">xmlns:x<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"http:&#47;&#47;schemas.microsoft.com&#47;winfx&#47;2006&#47;xaml"<&#47;span><span class="code-blue">><&#47;span><br />
  <span class="code-blue"><<&#47;span><strong><span class="code-brown">Ellipse<&#47;span><&#47;strong> <span class="code-red">Height<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"200"<&#47;span> <span class="code-red">Width<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"200"<&#47;span> <span class="code-red">Canvas.Left<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"30"<&#47;span> <span class="code-red">Canvas.Top<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"30"<&#47;span><br />
      <span class="code-red">Stroke<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"Black"<&#47;span> <span class="code-red">StrokeThickness<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"10"<&#47;span> <span class="code-red">Fill<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"SlateBlue"<&#47;span><span class="code-blue">&#47;><&#47;span><br />
  <span class="code-blue"><<&#47;span><strong><span class="code-brown">Rectangle<&#47;span><&#47;strong> <span class="code-red">Height<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"100"<&#47;span> <span class="code-red">Width<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"100"<&#47;span> <span class="code-red">Canvas.Left<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"5"<&#47;span> <span class="code-red">Canvas.Top<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"5"<&#47;span><br />
      <span class="code-red">Stroke<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"Black"<&#47;span> <span class="code-red">StrokeThickness<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"10"<&#47;span> <span class="code-red">Fill<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"SlateBlue"<&#47;span><span class="code-blue">&#47;><&#47;span><br />
  <span class="code-blue"><<&#47;span><strong><span class="code-brown">Line<&#47;span><&#47;strong> <span class="code-red">X1<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"280"<&#47;span> <span class="code-red">Y1<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"10"<&#47;span> <span class="code-red">X2<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"10"<&#47;span> <span class="code-red">Y2<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"280"<&#47;span><br />
      <span class="code-red">Stroke<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"black"<&#47;span> <span class="code-red">StrokeThickness<&#47;span><span class="code-blue">=<&#47;span><span class="code-blue">"5"<&#47;span><span class="code-blue">&#47;><&#47;span><br />
<span class="code-blue"><&#47;<&#47;span><span class="code-brown">Canvas<&#47;span><span class="code-blue">><&#47;span><&#47;pre><br />
Wir sehen hier als Wurzelelement das Canvas ("Leinwand") Tag. In Version 2 wird dieses Element zum "Child-Elment" degradiert, und ein neues Wurzelelement entworfen, was den Vorteil bietet, &Atilde;&frac14;ber mehrere Canvas in einer XAML zu verf&Atilde;&frac14;gen. Innerhalb eines Canvas lassen sich nun beliebige Objekte einbinden, in diesem Beispiel eine Ellipse, ein Viereck und eine Linie. Dar&Atilde;&frac14;ber hinaus gibt es eine Vielzahl an Steuerelementen und Designelementen, welche hier eingesetzt und kombiniert werden k&Atilde;&para;nnen. Um den Einstieg in XAML und damit in Silverlight besonders f&Atilde;&frac14;r Webentwickler einfach zu machen, wirkt die Sprache HTML &Atilde;&curren;hnlich. Auch gelten aus dessen Umfeld bekannte Grunds&Atilde;&curren;tze, wie beispielsweise, dass sp&Atilde;&curren;ter definierte Elemente per Default sich Oberhalb der &Atilde;&frac14;brigen Objekte befinden. Auch das aus HTML bekannte Box-Model (die beliebten div-Boxen) findet sich in &Atilde;&curren;hnlicher Weise wieder, denn Elemente, die innerhalb von anderen Elementen definiert wurden, werden so relativ zu ihren "Eltern-Elementen" positioniert. Besonders auffallend jedoch ist, dass alle Layoutangaben innerhalb des XML Dokuments definiert werden und sich oft als Attributwerte wiederfinden. Dieser "R&Atilde;&frac14;ckschritt" im Vergleich zum entschlackten XHTML, das sein Layout ausschlie&Atilde;&Yuml;lich &Atilde;&frac14;ber eine CSS erh&Atilde;&curren;lt wurde durch den Umstand dargelegt, dass dynamische Abl&Atilde;&curren;ufe auch in CSS nicht definiert sind und man daher gezwungen war einen eigenen Standard hierf&Atilde;&frac14;r zu definieren. Wahrscheinlicher ist aber, dass XML-Dateien f&Atilde;&frac14;r ein grafisches Entwickler-Tool, mit Hilfe dessen man ein User Interface erstellen kann, einfacher handhabbar ist. Mit Blend steht dem Designer eben ein solches Tool zur Verf&Atilde;&frac14;gung. Ein direktes Oberfl&Atilde;&curren;chencoding ist zwar m&Atilde;&para;glich, wurde vermutlich jedoch bereits w&Atilde;&curren;hrend des Sprachdesigns nicht pr&Atilde;&curren;feriert. Diese These wird auch durch die nicht vorhandenen deklarativen Operationsm&Atilde;&para;glichkeiten, wie arithmetische Operationen oder Validierungen, untermauert. Das XForms Model bietet in diesem Bereich wesentlich mehr deklarativer M&Atilde;&para;glichkeiten bereits Daten zu verarbeiten. Daher w&Atilde;&curren;re ein Vergleich alleine von XAML mit XHTML und SMIL anstelle von XForms angebrachter.</p>
<h2>Von XAML zu Silverlight<&#47;h2><br />
Damit XAML jedoch nicht nur ein Dateiformat zur repr&Atilde;&curren;sentation von UIs bleibt, kann zu jeder XAML-Datei eine "Code-Behind" Datei existieren, welche sich um die Eingabelogik und dar&Atilde;&frac14;ber hinaus m&Atilde;&para;glicherweise auch um die Gesch&Atilde;&curren;ftslogik k&Atilde;&frac14;mmert. Diese Code-Behind-Dateien k&Atilde;&para;nnen JavaScript Dateien sein, oder aber C# Dateien. Durch C# wird nun der Clientseite eine sehr m&Atilde;&curren;chtige, gleichwohl aber einfache Sprache zur Verf&Atilde;&frac14;gung gestellt. Somit kann jedem XAML-Objekt ein Event zugewiesen werden, welches mit Hilfe der Code Behind Datei verarbeitet wird. Angenehm hervorzuheben ist, dass diese Code Behind Dateien dynamisch zur Laufzeit XAML-Objekte erstellen und auch l&Atilde;&para;schen k&Atilde;&para;nnen. So ist eine noch dynamischere Oberfl&Atilde;&curren;che ohne zwischenzeitliche Serverzugriffe m&Atilde;&para;glich. (Diese M&Atilde;&para;glichkeit besteht in XForms nur via der XML-Events Definition, welche hierf&Atilde;&frac14;r auch die M&Atilde;&para;glichkeit bietet JavaScript einzubinden). Besonders einfach ist die Verbindung der beiden Schichten (XAML repr&Atilde;&curren;sentiert hierbei die VIEW, die Code Behind Datei das VIEWMODEL). Da jedem XAML Objekt ein Name zugewiesen werden kann, kann aus der Code Behind Datei direkt auf jedes dieser Elemente zugegriffen werden. F&Atilde;&frac14;r die meisten XAML Objekte existieren bereits umfassende vorimplementierte Methoden, die nur noch auf das Objekt angewendet werden m&Atilde;&frac14;ssen. Auch einen Trigger einzurichten, welcher Events an der UI abf&Atilde;&curren;ngt und diese an den Event Handler weitergibt erinnert an HTML mit JavaScript und ist daher besonders f&Atilde;&frac14;r Webentwickler einfach umzusetzen. Der Event Handler wird selbst durch eine Funktion, einer Methode in der Code Behind Datei implementiert.</p>
<p>Microsoft stellt insgesamt eine sehr gelungene Entwicklungsumgebung mit Blend und Visual Studio 2008 zur Verf&Atilde;&frac14;gung und bietet mit Silverlight welches XAML integriert, ein beeindruckendes Framework. Besonders interessant w&Atilde;&curren;re noch, ob es m&Atilde;&para;glich ist ein XAML-UI mit dem XForms-Model zu kombinieren. Tests hierzu werde ich die kommenden Tage machen und sie hier zur Verf&Atilde;&frac14;gung stellen.<br />
Gewisse Kritik muss sich Microsoft jedoch f&Atilde;&frac14;r die Entscheidung Struktur und Layout der Oberfl&Atilde;&curren;che wieder in eine Datei zusammen zu f&Atilde;&frac14;hren und nicht auf das Paradigma der Modularit&Atilde;&curren;t zu vertrauen, gefallen lassen. Hier w&Atilde;&curren;re meiner Meinung nach eine Weiterentwicklung von SMIL vielleicht doch die bessere Variante gewesen. F&Atilde;&frac14;r die Entscheidung Microsofts spricht die typische "All-In-One" L&Atilde;&para;sung, welche hier daf&Atilde;&frac14;r sorgt, dass die Umsetzung von RIAs mit Hilfe Microsofts Entwicklungsumgebungen sehr einfach von statten gehen kann. Das Hauptproblem wird hierbei vielmehr an der Koordination zwischen den "Designern" und den "Code Behind" schreiben liegen und an der Tatsache, dass viele Designer mit Apples Mac arbeiten, f&Atilde;&frac14;r welchen momentan noch keine Portierungen von Blend zur Verf&Atilde;&frac14;gung stehen.</p>
<p>Die n&Atilde;&curren;chste Folge dieser Reihe wird etwas auf sich warten lassen m&Atilde;&frac14;ssen, da ich mir momentan noch nicht sicher bin, ob ich als n&Atilde;&curren;chstes Adobes MXML oder Apples Framework f&Atilde;&frac14;r RIAs vostellen werde. Irgendwann in den kommenden Tagen, sp&Atilde;&curren;testens kommende Woche, wird diese Reihe sicher fortgesetzt.</p>
<h3>Weblinks<&#47;h3></p>
<ul>
<li>http:&#47;&#47;www.artima.com&#47;forums&#47;flat.jsp?forum=152&amp;thread=231366<&#47;li>
<li>http:&#47;&#47;msdn.microsoft.com&#47;en-us&#47;library&#47;cc189036(VS.95).aspx<&#47;li><br />
<&#47;ul></p>
