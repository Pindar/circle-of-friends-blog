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
excerpt: Während den Vorbereitungen auf Windows Vista wurde auch an
  einer neuen Sprache gearbeitet, die es Entwicklern einfacher machen sollte, Anwendungen
  grafisch ansprechender schreiben zu können und das mit geringerem Aufwand.
  Microsoft arbeitete daher an "Avalon" für Windows "Longhorn", aus
  welchem die "Windows Presentation Foundation" (WPF) hervorging. Diese Entwicklungen
  brachte die deklarative Sprache XAML hervor, mit Hilfe derer man Oberflächen
  via einer XML-Datei beschreiben kann, ähnlich XHTML zusammen mit
  SMIL. Microsofts Silverlight ist eine Teilmenge von WPF. Für Silverlightche
  gibt es Laufzeitumgebungen als Plug-In auch für nicht Microsoft-Produkte,
  wie dem Firefox und Safari. Des weiteren wird Silverlight auch auf weiteren Plattformen,
  wie Apples Macintosh und Linux (hier unter dem Namen "Moonlight"), unterstützt.
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
    öffentlich dokumentiert ist, und alle bisherigen tiefer gehenden
    Informationen aus einem OpenSource-Projekt stammen, auf dem Apple aufbaut. Stimmt
    das soweit?
---
<p>Während den Vorbereitungen auf Windows Vista wurde auch an einer neuen Sprache gearbeitet, die es Entwicklern einfacher machen sollte, Anwendungen grafisch ansprechender schreiben zu können und das mit geringerem Aufwand. Microsoft arbeitete daher an "Avalon" für Windows "Longhorn", aus welchem die "Windows Presentation Foundation" (WPF) hervorging. Diese Entwicklungen brachte die deklarative Sprache XAML hervor, mit Hilfe derer man Oberflächen via einer XML-Datei beschreiben kann, ähnlich XHTML zusammen mit SMIL. Microsofts Silverlight ist eine Teilmenge von WPF. Für Silverlightche gibt es Laufzeitumgebungen als Plug-In auch für nicht Microsoft-Produkte, wie dem Firefox und Safari. Des weiteren wird Silverlight auch auf weiteren Plattformen, wie Apples Macintosh und Linux (hier unter dem Namen "Moonlight"), unterstützt. Es Positioniert sich folglich gegen Adobe AIR.<a id="more"></a><a id="more-122"></a></p>
<h2>Aufbau von XAML</h2><br />
XAML selbst ist, wie bereits erwähnt eine Sprache, die deklarativ ein User Interface (UI) beschreibt. Der Mehrwert gegenüber dem offenen XHTML-Standard bietet die Sprache in der Animationsfähigkeit von Objekten. Da Microsoft auch an der Entwicklung von SMIL, dem offenen, ebenfalls auf XML basierenden W3-Standard, beteiligt war und selbst SMIL 2.0 fast vollständig seit Version 5 des Internet Explorers implementierte, verwundert eine gewisse syntaktische &Atilde;&bdquo;hnlichkeit der beiden Sprachen nicht. Viel mehr verwundert jedoch, dass Microsoft überhaupt an einem neuen Standard arbeitete und nicht den bereits existierenden offenen w3 Standard einfach weiterentwickelt wiederverwendet hat. Auch wurden in einigen <a href="http://www.simplegeek.com/PermaLink.aspx/b7e02709-0112-4977-9b73-1aa9d471a570" target="_blank">Blog-Beiträgen</a> Probleme diskutiert, welche <a href="http://www.w3.org/1999/08/WD-smil-boston-19990803/Integrate/Time-Integrate#CSSFramework" target="_blank">bereits Jahre zuvor</a> ebenfalls im SMIL-Lager (unter sehr starker Microsoft-Beteiligung) diskutiert wurden, was einer entsprechende "süffisanz" nicht abträglich wird.</p>
<p>Nun aber ein Beispiel-Code einer typischen XAML-Anwendung (Von <a href="http://www.silverlight.net/quickstarts/silverlight10/drawing.aspx" target="_blank">Silverlight Quickstart</a> entnommen):</p>
<pre><span class="code-blue"><</span><span class="code-brown">Canvas</span><br />
    <span class="code-red">xmlns</span><span class="code-blue">=</span><span class="code-blue">"http://schemas.microsoft.com/client/2007"</span><br />
    <span class="code-red">xmlns:x</span><span class="code-blue">=</span><span class="code-blue">"http://schemas.microsoft.com/winfx/2006/xaml"</span><span class="code-blue">></span><br />
  <span class="code-blue"><</span><strong><span class="code-brown">Ellipse</span></strong> <span class="code-red">Height</span><span class="code-blue">=</span><span class="code-blue">"200"</span> <span class="code-red">Width</span><span class="code-blue">=</span><span class="code-blue">"200"</span> <span class="code-red">Canvas.Left</span><span class="code-blue">=</span><span class="code-blue">"30"</span> <span class="code-red">Canvas.Top</span><span class="code-blue">=</span><span class="code-blue">"30"</span><br />
      <span class="code-red">Stroke</span><span class="code-blue">=</span><span class="code-blue">"Black"</span> <span class="code-red">StrokeThickness</span><span class="code-blue">=</span><span class="code-blue">"10"</span> <span class="code-red">Fill</span><span class="code-blue">=</span><span class="code-blue">"SlateBlue"</span><span class="code-blue">/></span><br />
  <span class="code-blue"><</span><strong><span class="code-brown">Rectangle</span></strong> <span class="code-red">Height</span><span class="code-blue">=</span><span class="code-blue">"100"</span> <span class="code-red">Width</span><span class="code-blue">=</span><span class="code-blue">"100"</span> <span class="code-red">Canvas.Left</span><span class="code-blue">=</span><span class="code-blue">"5"</span> <span class="code-red">Canvas.Top</span><span class="code-blue">=</span><span class="code-blue">"5"</span><br />
      <span class="code-red">Stroke</span><span class="code-blue">=</span><span class="code-blue">"Black"</span> <span class="code-red">StrokeThickness</span><span class="code-blue">=</span><span class="code-blue">"10"</span> <span class="code-red">Fill</span><span class="code-blue">=</span><span class="code-blue">"SlateBlue"</span><span class="code-blue">/></span><br />
  <span class="code-blue"><</span><strong><span class="code-brown">Line</span></strong> <span class="code-red">X1</span><span class="code-blue">=</span><span class="code-blue">"280"</span> <span class="code-red">Y1</span><span class="code-blue">=</span><span class="code-blue">"10"</span> <span class="code-red">X2</span><span class="code-blue">=</span><span class="code-blue">"10"</span> <span class="code-red">Y2</span><span class="code-blue">=</span><span class="code-blue">"280"</span><br />
      <span class="code-red">Stroke</span><span class="code-blue">=</span><span class="code-blue">"black"</span> <span class="code-red">StrokeThickness</span><span class="code-blue">=</span><span class="code-blue">"5"</span><span class="code-blue">/></span><br />
<span class="code-blue"></</span><span class="code-brown">Canvas</span><span class="code-blue">></span></pre><br />
Wir sehen hier als Wurzelelement das Canvas ("Leinwand") Tag. In Version 2 wird dieses Element zum "Child-Elment" degradiert, und ein neues Wurzelelement entworfen, was den Vorteil bietet, über mehrere Canvas in einer XAML zu verfügen. Innerhalb eines Canvas lassen sich nun beliebige Objekte einbinden, in diesem Beispiel eine Ellipse, ein Viereck und eine Linie. Darüber hinaus gibt es eine Vielzahl an Steuerelementen und Designelementen, welche hier eingesetzt und kombiniert werden können. Um den Einstieg in XAML und damit in Silverlight besonders für Webentwickler einfach zu machen, wirkt die Sprache HTML ähnlich. Auch gelten aus dessen Umfeld bekannte Grundsätze, wie beispielsweise, dass später definierte Elemente per Default sich Oberhalb der übrigen Objekte befinden. Auch das aus HTML bekannte Box-Model (die beliebten div-Boxen) findet sich in ähnlicher Weise wieder, denn Elemente, die innerhalb von anderen Elementen definiert wurden, werden so relativ zu ihren "Eltern-Elementen" positioniert. Besonders auffallend jedoch ist, dass alle Layoutangaben innerhalb des XML Dokuments definiert werden und sich oft als Attributwerte wiederfinden. Dieser "Rückschritt" im Vergleich zum entschlackten XHTML, das sein Layout ausschließlich über eine CSS erhält wurde durch den Umstand dargelegt, dass dynamische Abläufe auch in CSS nicht definiert sind und man daher gezwungen war einen eigenen Standard hierfür zu definieren. Wahrscheinlicher ist aber, dass XML-Dateien für ein grafisches Entwickler-Tool, mit Hilfe dessen man ein User Interface erstellen kann, einfacher handhabbar ist. Mit Blend steht dem Designer eben ein solches Tool zur Verfügung. Ein direktes Oberflächencoding ist zwar möglich, wurde vermutlich jedoch bereits während des Sprachdesigns nicht präferiert. Diese These wird auch durch die nicht vorhandenen deklarativen Operationsmöglichkeiten, wie arithmetische Operationen oder Validierungen, untermauert. Das XForms Model bietet in diesem Bereich wesentlich mehr deklarativer Möglichkeiten bereits Daten zu verarbeiten. Daher wäre ein Vergleich alleine von XAML mit XHTML und SMIL anstelle von XForms angebrachter.</p>
<h2>Von XAML zu Silverlight</h2><br />
Damit XAML jedoch nicht nur ein Dateiformat zur repräsentation von UIs bleibt, kann zu jeder XAML-Datei eine "Code-Behind" Datei existieren, welche sich um die Eingabelogik und darüber hinaus möglicherweise auch um die Geschäftslogik kümmert. Diese Code-Behind-Dateien können JavaScript Dateien sein, oder aber C# Dateien. Durch C# wird nun der Clientseite eine sehr mächtige, gleichwohl aber einfache Sprache zur Verfügung gestellt. Somit kann jedem XAML-Objekt ein Event zugewiesen werden, welches mit Hilfe der Code Behind Datei verarbeitet wird. Angenehm hervorzuheben ist, dass diese Code Behind Dateien dynamisch zur Laufzeit XAML-Objekte erstellen und auch löschen können. So ist eine noch dynamischere Oberfläche ohne zwischenzeitliche Serverzugriffe möglich. (Diese Möglichkeit besteht in XForms nur via der XML-Events Definition, welche hierfür auch die Möglichkeit bietet JavaScript einzubinden). Besonders einfach ist die Verbindung der beiden Schichten (XAML repräsentiert hierbei die VIEW, die Code Behind Datei das VIEWMODEL). Da jedem XAML Objekt ein Name zugewiesen werden kann, kann aus der Code Behind Datei direkt auf jedes dieser Elemente zugegriffen werden. Für die meisten XAML Objekte existieren bereits umfassende vorimplementierte Methoden, die nur noch auf das Objekt angewendet werden müssen. Auch einen Trigger einzurichten, welcher Events an der UI abfängt und diese an den Event Handler weitergibt erinnert an HTML mit JavaScript und ist daher besonders für Webentwickler einfach umzusetzen. Der Event Handler wird selbst durch eine Funktion, einer Methode in der Code Behind Datei implementiert.</p>
<p>Microsoft stellt insgesamt eine sehr gelungene Entwicklungsumgebung mit Blend und Visual Studio 2008 zur Verfügung und bietet mit Silverlight welches XAML integriert, ein beeindruckendes Framework. Besonders interessant wäre noch, ob es möglich ist ein XAML-UI mit dem XForms-Model zu kombinieren. Tests hierzu werde ich die kommenden Tage machen und sie hier zur Verfügung stellen.<br />
Gewisse Kritik muss sich Microsoft jedoch für die Entscheidung Struktur und Layout der Oberfläche wieder in eine Datei zusammen zu führen und nicht auf das Paradigma der Modularität zu vertrauen, gefallen lassen. Hier wäre meiner Meinung nach eine Weiterentwicklung von SMIL vielleicht doch die bessere Variante gewesen. Für die Entscheidung Microsofts spricht die typische "All-In-One" Lösung, welche hier dafür sorgt, dass die Umsetzung von RIAs mit Hilfe Microsofts Entwicklungsumgebungen sehr einfach von statten gehen kann. Das Hauptproblem wird hierbei vielmehr an der Koordination zwischen den "Designern" und den "Code Behind" schreiben liegen und an der Tatsache, dass viele Designer mit Apples Mac arbeiten, für welchen momentan noch keine Portierungen von Blend zur Verfügung stehen.</p>
<p>Die nächste Folge dieser Reihe wird etwas auf sich warten lassen müssen, da ich mir momentan noch nicht sicher bin, ob ich als nächstes Adobes MXML oder Apples Framework für RIAs vostellen werde. Irgendwann in den kommenden Tagen, spätestens kommende Woche, wird diese Reihe sicher fortgesetzt.</p>
<h3>Weblinks</h3></p>
<ul>
<li>http://www.artima.com/forums/flat.jsp?forum=152&amp;thread=231366</li>
<li>http://msdn.microsoft.com/en-us/library/cc189036(VS.95).aspx</li><br />
</ul></p>
