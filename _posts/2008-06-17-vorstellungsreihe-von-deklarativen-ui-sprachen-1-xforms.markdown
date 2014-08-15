---
layout: post
status: publish
published: true
title: Vorstellungsreihe von deklarativen UI-Sprachen (1) XForms
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
excerpt: Wie bereits angek&Atilde;&frac14;ndigt stelle ich euch einige der wichtigsten
  auf dem Markt befindlichen deklarativen User-Interface (UI) Beschreibungssprachen
  f&Atilde;&frac14;r "Rich Internet applications" (RIAs) in einer kleinen Blog-Reihe
  vor. Beginnen m&Atilde;&para;chte ich diese Reihe gleich mit einem Standard, den
  ich bereits in meinen beiden letzten Blogeintr&Atilde;&curren;gen erw&Atilde;&curren;hnte
  und der zugleich eine Sonderrolle innerhalb der XML basierten UI Sprachen einnimmt.
wordpress_id: 119
wordpress_url: http://www.pindarsign.de/webblog/?p=119
date: '2008-06-17 19:05:51 +0200'
date_gmt: '2008-06-17 17:05:51 +0200'
categories:
- Technik
- Rich Internet Application
tags:
- xml
- xforms
comments: []
---
<p>Wie bereits angek&Atilde;&frac14;ndigt stelle ich euch einige der wichtigsten auf dem Markt befindlichen deklarativen User-Interface (UI) Beschreibungssprachen f&Atilde;&frac14;r "Rich Internet applications" (RIAs) in einer kleinen Blog-Reihe vor. Beginnen m&Atilde;&para;chte ich diese Reihe gleich mit einem Standard, den ich bereits in meinen beiden letzten Blogeintr&Atilde;&curren;gen erw&Atilde;&curren;hnte und der zugleich eine Sonderrolle innerhalb der XML basierten UI Sprachen einnimmt.<a id="more"></a><a id="more-119"></a></p>
<p>XForms ist genau genommen n&Atilde;&curren;mlich noch kein vollst&Atilde;&curren;ndiges UI. Es stellt nur ein XML-Modul zur Verf&Atilde;&frac14;gung, mit Hilfe dessen "fortgeschrittene Eingabetechniken" in XML-basierten Dokumenten genutzt werden k&Atilde;&para;nnen. Diese "fortgeschrittenen Eingabetechniken" wurden als Weiterentwicklung der bekannten HTML-Formulare geplant, sind aber weit mehr als das und es ist zu vermuten, dass XForms-Module deshalb auch nicht abw&Atilde;&curren;rtskompatibel sind.<a href="http:&#47;&#47;www.pindarsign.de&#47;webblog&#47;wp-content&#47;uploads&#47;2008&#47;06&#47;xforms-uebersicht.png"><img class="alignright size-medium wp-image-120" style="float: right;" title="XForms Model Eingliederung" src="http:&#47;&#47;www.pindarsign.de&#47;webblog&#47;wp-content&#47;uploads&#47;2008&#47;06&#47;xforms-uebersicht-196x300.png" alt="(c) w3c" width="196" height="300" &#47;><&#47;a> Eine neben l&Atilde;&curren;ufige Entwicklung, die hier zumindest eine kurze Erw&Atilde;&curren;hnung finden soll, stellt der Standard Web Forms 2.0 dar, welcher in die HTML 5 Bem&Atilde;&frac14;hungen integriert ist und eine Br&Atilde;&frac14;cke zwischen konventionellen Formularen und dem XForms-Standard schlagen soll.</p>
<p>Nun aber wieder zur&Atilde;&frac14;ck zu XForms. Die XForms-Spezifikation wurde nicht in alleiniger Regie einer einzelnen Firma konzipiert, sondern entspringt aus dem W3 Konsortium. Es integriert sich daher besonders gut in die &Atilde;&frac14;brigen W3-Spezifikationen.</p>
<p>Wie passt nun XForms trotzdem zum Blickwinkel einer UI?</p>
<p>XForms ist in zwei, bzw. drei Teilmodule Aufgeteilt. Dem XForms-Model, in welchem wiederum eine XML-basierte Dateninstanz integriert ist und dem XForms UI. Dieses UI Model alleine stellt alle relevanten Eingabem&Atilde;&para;glichkeiten, wie Input-Felder, Radio-Buttons, Regler, herk&Atilde;&para;mmliche Buttons und viele Eingabem&Atilde;&para;glichkeiten mehr zur Verf&Atilde;&frac14;gung. Da die Spezifikation nichts &Atilde;&frac14;ber das detaillierte Aussehen der Elemente vorschreibt, k&Atilde;&para;nnen die entsprechenden Elemente device-unabh&Atilde;&curren;ngig programmiert werden, jedoch device-abh&Atilde;&curren;ngig von der jeweiligen Renderingsoftware dargestellt werden. Damit ist XForms nicht nur Plattformunabh&Atilde;&curren;ngig, sondern auch Device-Unabh&Atilde;&curren;ngig. Da XForms UI-Elemente meist in eine XHTML-Struktur (oder eine andere Struktursprache) eingebunden ist, kann die Darstellung mit CSS 3 im Rahmen der CSS-M&Atilde;&para;glichkeiten beeinflusst werden. Beispielsweise die Farbgebung, die Schriftwahl etc. (Da f&Atilde;&frac14;r verschiedene devices auch verschiedene CSS ausgew&Atilde;&curren;hlt werden k&Atilde;&para;nnen, schr&Atilde;&curren;nkt dies oben erw&Atilde;&curren;hnte Unabh&Atilde;&curren;ngigkeit nicht ein).<br />
Der Hauptnutzen liegt aber darin, dass es nicht nur Eingabewerkzeuge bereitstellt, sondern der Model-Teil dar&Atilde;&frac14;ber hinaus fast alle "Funktionen" zur Verf&Atilde;&frac14;gung stellt, die zu einer RIAs ben&Atilde;&para;tigt werden, welche aber alle deklarativ beschreibbar aufgerufen werden k&Atilde;&para;nnen. Um die zentralsten Elemente vorstellen zu k&Atilde;&para;nnen, bediene ich mich eines Beispielszenarios (<a href="http:&#47;&#47;www.ibm.com&#47;developerworks&#47;xml&#47;library&#47;x-xformsintro2&#47;index.html?S_TACT=105AGX06&amp;S_CMP=EDU" target="_blank">von IBM entnommen<&#47;a>):</p>
<pre class="displaycode"><?xml version="1.0" encoding="UTF-8"?><br />
<html xmlns="http:&#47;&#47;www.w3.org&#47;1999&#47;xhtml"<br />
    xmlns:xf="http:&#47;&#47;www.w3.org&#47;2002&#47;xforms"><br />
<head><br />
<title>Search Form<&#47;title><br />
<xf:model><br />
    <xf:instance src="http:&#47;&#47;localhost&#47;~chrish&#47;data.xml"&#47;><br />
    <xf:submission action="http:&#47;&#47;localhost&#47;~chrish&#47;data.xml"<br />
        method="put" id="submit-edit"&#47;><br />
<&#47;xf:model><br />
<&#47;head><br />
<body></p>
<h1>XPath<&#47;h1></p>
<p>
Change the info and status!<br />
<&#47;p></p>
<p>
<xf:input ref="some&#47;additional&#47;info"><xf:label>New<br />
info:<&#47;xf:label><&#47;xf:input><br&#47;><br />
<xf:input ref="some&#47;additional&#47;info&#47;@status"><xf:label>New<br />
status:<&#47;xf:label><&#47;xf:input><br />
<xf:submit<br />
submission="submit-edit"><xf:label>Save<&#47;xf:label><&#47;xf:submit><br />
<&#47;p><br />
<&#47;body><br />
<&#47;html><&#47;pre><br />
Mit Hilfe dieses XHTML+XForms Code ist es m&Atilde;&para;glich eine zweite XHTML-Seite, genauer die unter "submission" genannte data.xml Datei zu editieren. Im <head>-Bereich der XHTML-Seite ist immer der Model-Bereich von XForms einzutragen. In diesem Beispiel wird hier nur auf eine Daten-"Instanz" verwiesen und ein submission definiert. Die Instanz beschreibt die Daten, welche durch das Formular ganz oder teilweise repr&Atilde;&curren;sentiert wird. Hier k&Atilde;&para;nnen alle Felder definiert werden, welche von XForms ausgef&Atilde;&frac14;llt werden sollen. Der submission-Tag beschreibt das, was Action in HTML &Atilde;&curren;hnlich beschrieben hat, jedoch entsprechend mit etwas mehr M&Atilde;&para;glichkeiten. Denn durch die Trennung des submission-Tags von der eigentlichen UI, die im Body-Bereich der XHTML-Seite definiert ist, k&Atilde;&para;nnen mehrere Submit-Buttons zu unterschiedlichen Zielen f&Atilde;&frac14;hren. Die Bindung der beiden Bereiche wird &Atilde;&frac14;ber die jeweilige und eindeutige "id" im Model-Bereich hergestellt. Durch die Integration von XPath kann die Bindung von Input-Feldern auch auf Datenelemente in der Instanz durchgef&Atilde;&frac14;hrt werden, wie es im Beispiel durch ref="some&#47;additional&#47;info&#47;@status" vorgef&Atilde;&frac14;hrt wird. Aufgrund der Komplexen M&Atilde;&para;glichkeiten m&Atilde;&para;chte ich diese im Folgenden nur noch aufz&Atilde;&curren;hlen, sie jedoch nicht mehr mit Beispielen visualisieren. F&Atilde;&frac14;r den tieferen Einstieg empfehle ich die <a href="http:&#47;&#47;www.ibm.com&#47;developerworks&#47;xml&#47;library&#47;x-xformsintro1&#47;index.html?S_TACT=105AGX06&amp;S_CMP=EDU" target="_blank">Einf&Atilde;&frac14;hrung von IBM<&#47;a> oder f&Atilde;&frac14;r <a href="http:&#47;&#47;www.w3.org&#47;MarkUp&#47;Forms&#47;2003&#47;xforms-for-html-authors.html" target="_blank">HTML-Umsteiger ein Dokument<&#47;a> des W3C.</p>
<p>Die XForms-Technologie stellt unter anderem folgende Funktionalit&Atilde;&curren;t bereit:</p>
<ul>
<li>Eingegebene Daten k&Atilde;&para;nnen mit Hilfe des XForms-Model gegen selbst erstellte Datentypen, die ebenfalls deklarativ definiert sind, validiert werden. Leider ist im Standard nicht festgelegt, wie eine visuelle Warnung im Ausnahmefall auszusehen hat.<&#47;li>
<li>Mit Hilfe von XForms k&Atilde;&para;nnen beim Absenden der Daten diese als XML an den Server &Atilde;&frac14;bermitteln werden und daher ist diese Technik besonders f&Atilde;&frac14;r SOA interessant.<&#47;li>
<li>Arithmetische Berechnungen stehen sowohl im UI als auch im Model zur Verf&Atilde;&frac14;gung.<&#47;li>
<li>Durch die Datenbindung zwischen Model und UI k&Atilde;&para;nnen eingegebene Daten automatisch aktualisiert werden (beispielsweise bei einer Warenliste wird der Endpreis automatisch berechnet und angezeigt, ohne dass sich der Programmierer oder der Anwender speziell um das Ausl&Atilde;&para;sen eines&Acirc;&nbsp; "neu berechnen" Events k&Atilde;&frac14;mmern m&Atilde;&frac14;sste).<&#47;li>
<li>F&Atilde;&frac14;r Events und Actions (in HTML unter "onclick" usw. bekannt) wird nun einheitlich der <a href="http:&#47;&#47;www.w3.org&#47;TR&#47;xml-events" target="_blank">XML-Events<&#47;a> Standard genutzt und bietet so noch umfangreichere M&Atilde;&para;glichkeiten.<&#47;li>
<li>Durch "switching" ist eine teilweise Sichtbarkeit eines sehr umfangreichen Formulars oder das Einblenden ausschlie&Atilde;&Yuml;lich f&Atilde;&frac14;r den Benutzer durch seine bisherigen Eingaben bedingten relevanten Eingabefelder m&Atilde;&para;glich. Ein Formular muss somit nicht mehr &Atilde;&frac14;ber mehrere HTML-Seiten aufgeteilt werden, was bei herk&Atilde;&para;mmlicher HTML-Technik zu Problemen mit der Speicherung von den tempor&Atilde;&curren;r eingegebenen Daten f&Atilde;&frac14;hrte.<&#47;li>
<li>Lokales Zwischenspeichern von Formulardaten ist in XML-Dateien (einer lokalen Instanz-Datei) m&Atilde;&para;glich. Besonders f&Atilde;&frac14;r sehr mobile Dienste ist dies interessant, denen keine permanente Internetverbindung zur Verf&Atilde;&frac14;gung steht.<&#47;li>
<li>Durch die verst&Atilde;&curren;rkte Clientbasierte Eingabelogik-Implementierungsm&Atilde;&para;glichkeiten sind erheblich weniger Serverzugriffe zu erwarten, was zu einer geringeren Auslastung der Bandbreite und auch des Servers f&Atilde;&frac14;hrt. Ebenfalls sind Standalone Anwendungen ohne eines (Web)Servers denkbar, da die Nutzung von JavaScript&acirc;&bdquo;&cent; zur Implementation der Gesch&Atilde;&curren;ftslogik m&Atilde;&para;glich ist.<&#47;li><br />
<&#47;ul><br />
Insgesamt gesehen stellt XForms eine sehr interessante Technik bereit, die zu RIAs f&Atilde;&frac14;hrt, welche fast vollst&Atilde;&curren;ndig ohne Scripting auskommen. Besonders in sicherheitsrelevanten Bereichen ist dieser Ansatz von hoher Prisanz. Auch die Optik muss dabei nicht zwangsweise leiden, da XForms zusammen mit SVG, CSS und SMIL einsetzt werden k&Atilde;&para;nnte. Diese Standards definieren grafische, visualisierende und dynamische Pr&Atilde;&curren;sentations-M&Atilde;&para;glichkeiten. Mit der theoretischen M&Atilde;&para;glichkeit das XForms-Model zusammen mit propriet&Atilde;&curren;ren L&Atilde;&para;sungen nutzen zu k&Atilde;&para;nnen, st&Atilde;&frac14;nde auch MS Silverlight oder Flash zur Visualisierung der Daten mit der Power von XForms-Model zur Verf&Atilde;&frac14;gung. F&Atilde;&frac14;r diese Kombination gibt es derzeit aber keine oder zumindest nicht im Internet offensichtlich auffindbare Beispiele. Leider ist dar&Atilde;&frac14;ber hinaus der XForms Standard momentan noch in keinem g&Atilde;&curren;ngigen Internetbrowser fester Bestandteil und muss als Browsererweiterung installiert werden. Diese Erweiterungen basieren oft auf JavaScript implementierungen des Standards und sind f&Atilde;&frac14;r fast alle Browser verf&Atilde;&frac14;gbar.<br />
Hoffentlich wird dieser Standard bald fester Bestandteil jedes Browsers!</p>
<p>In der n&Atilde;&curren;chsten Folge werde ich Microsofts eigenen Ansatz XAML vorstellen.</p>
<p>(Das Copyright der Abbildung liegt beim w3c).</p>
