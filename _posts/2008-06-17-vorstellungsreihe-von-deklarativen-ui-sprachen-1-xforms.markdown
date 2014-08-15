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
excerpt: Wie bereits angekündigt stelle ich euch einige der wichtigsten
  auf dem Markt befindlichen deklarativen User-Interface (UI) Beschreibungssprachen
  für "Rich Internet applications" (RIAs) in einer kleinen Blog-Reihe
  vor. Beginnen möchte ich diese Reihe gleich mit einem Standard, den
  ich bereits in meinen beiden letzten Blogeinträgen erwähnte
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
<p>Wie bereits angekündigt stelle ich euch einige der wichtigsten auf dem Markt befindlichen deklarativen User-Interface (UI) Beschreibungssprachen für "Rich Internet applications" (RIAs) in einer kleinen Blog-Reihe vor. Beginnen möchte ich diese Reihe gleich mit einem Standard, den ich bereits in meinen beiden letzten Blogeinträgen erwähnte und der zugleich eine Sonderrolle innerhalb der XML basierten UI Sprachen einnimmt.<a id="more"></a><a id="more-119"></a></p>
<p>XForms ist genau genommen nämlich noch kein vollständiges UI. Es stellt nur ein XML-Modul zur Verfügung, mit Hilfe dessen "fortgeschrittene Eingabetechniken" in XML-basierten Dokumenten genutzt werden können. Diese "fortgeschrittenen Eingabetechniken" wurden als Weiterentwicklung der bekannten HTML-Formulare geplant, sind aber weit mehr als das und es ist zu vermuten, dass XForms-Module deshalb auch nicht abwärtskompatibel sind.<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/06/xforms-uebersicht.png"><img class="alignright size-medium wp-image-120" style="float: right;" title="XForms Model Eingliederung" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/06/xforms-uebersicht-196x300.png" alt="(c) w3c" width="196" height="300" /></a> Eine neben läufige Entwicklung, die hier zumindest eine kurze Erwähnung finden soll, stellt der Standard Web Forms 2.0 dar, welcher in die HTML 5 Bemühungen integriert ist und eine Brücke zwischen konventionellen Formularen und dem XForms-Standard schlagen soll.</p>
<p>Nun aber wieder zurück zu XForms. Die XForms-Spezifikation wurde nicht in alleiniger Regie einer einzelnen Firma konzipiert, sondern entspringt aus dem W3 Konsortium. Es integriert sich daher besonders gut in die übrigen W3-Spezifikationen.</p>
<p>Wie passt nun XForms trotzdem zum Blickwinkel einer UI?</p>
<p>XForms ist in zwei, bzw. drei Teilmodule Aufgeteilt. Dem XForms-Model, in welchem wiederum eine XML-basierte Dateninstanz integriert ist und dem XForms UI. Dieses UI Model alleine stellt alle relevanten Eingabemöglichkeiten, wie Input-Felder, Radio-Buttons, Regler, herkömmliche Buttons und viele Eingabemöglichkeiten mehr zur Verfügung. Da die Spezifikation nichts über das detaillierte Aussehen der Elemente vorschreibt, können die entsprechenden Elemente device-unabhängig programmiert werden, jedoch device-abhängig von der jeweiligen Renderingsoftware dargestellt werden. Damit ist XForms nicht nur Plattformunabhängig, sondern auch Device-Unabhängig. Da XForms UI-Elemente meist in eine XHTML-Struktur (oder eine andere Struktursprache) eingebunden ist, kann die Darstellung mit CSS 3 im Rahmen der CSS-Möglichkeiten beeinflusst werden. Beispielsweise die Farbgebung, die Schriftwahl etc. (Da für verschiedene devices auch verschiedene CSS ausgewählt werden können, schränkt dies oben erwähnte Unabhängigkeit nicht ein).<br />
Der Hauptnutzen liegt aber darin, dass es nicht nur Eingabewerkzeuge bereitstellt, sondern der Model-Teil darüber hinaus fast alle "Funktionen" zur Verfügung stellt, die zu einer RIAs benötigt werden, welche aber alle deklarativ beschreibbar aufgerufen werden können. Um die zentralsten Elemente vorstellen zu können, bediene ich mich eines Beispielszenarios (<a href="http://www.ibm.com/developerworks/xml/library/x-xformsintro2/index.html?S_TACT=105AGX06&amp;S_CMP=EDU" target="_blank">von IBM entnommen</a>):</p>
<pre class="displaycode"><?xml version="1.0" encoding="UTF-8"?><br />
<html xmlns="http://www.w3.org/1999/xhtml"<br />
    xmlns:xf="http://www.w3.org/2002/xforms"><br />
<head><br />
<title>Search Form</title><br />
<xf:model><br />
    <xf:instance src="http://localhost/~chrish/data.xml"/><br />
    <xf:submission action="http://localhost/~chrish/data.xml"<br />
        method="put" id="submit-edit"/><br />
</xf:model><br />
</head><br />
<body></p>
<h1>XPath</h1></p>
<p>
Change the info and status!<br />
</p></p>
<p>
<xf:input ref="some/additional/info"><xf:label>New<br />
info:</xf:label></xf:input><br/><br />
<xf:input ref="some/additional/info/@status"><xf:label>New<br />
status:</xf:label></xf:input><br />
<xf:submit<br />
submission="submit-edit"><xf:label>Save</xf:label></xf:submit><br />
</p><br />
</body><br />
</html></pre><br />
Mit Hilfe dieses XHTML+XForms Code ist es möglich eine zweite XHTML-Seite, genauer die unter "submission" genannte data.xml Datei zu editieren. Im <head>-Bereich der XHTML-Seite ist immer der Model-Bereich von XForms einzutragen. In diesem Beispiel wird hier nur auf eine Daten-"Instanz" verwiesen und ein submission definiert. Die Instanz beschreibt die Daten, welche durch das Formular ganz oder teilweise repräsentiert wird. Hier können alle Felder definiert werden, welche von XForms ausgefüllt werden sollen. Der submission-Tag beschreibt das, was Action in HTML ähnlich beschrieben hat, jedoch entsprechend mit etwas mehr Möglichkeiten. Denn durch die Trennung des submission-Tags von der eigentlichen UI, die im Body-Bereich der XHTML-Seite definiert ist, können mehrere Submit-Buttons zu unterschiedlichen Zielen führen. Die Bindung der beiden Bereiche wird über die jeweilige und eindeutige "id" im Model-Bereich hergestellt. Durch die Integration von XPath kann die Bindung von Input-Feldern auch auf Datenelemente in der Instanz durchgeführt werden, wie es im Beispiel durch ref="some/additional/info/@status" vorgeführt wird. Aufgrund der Komplexen Möglichkeiten möchte ich diese im Folgenden nur noch aufzählen, sie jedoch nicht mehr mit Beispielen visualisieren. Für den tieferen Einstieg empfehle ich die <a href="http://www.ibm.com/developerworks/xml/library/x-xformsintro1/index.html?S_TACT=105AGX06&amp;S_CMP=EDU" target="_blank">Einführung von IBM</a> oder für <a href="http://www.w3.org/MarkUp/Forms/2003/xforms-for-html-authors.html" target="_blank">HTML-Umsteiger ein Dokument</a> des W3C.</p>
<p>Die XForms-Technologie stellt unter anderem folgende Funktionalität bereit:</p>
<ul>
<li>Eingegebene Daten können mit Hilfe des XForms-Model gegen selbst erstellte Datentypen, die ebenfalls deklarativ definiert sind, validiert werden. Leider ist im Standard nicht festgelegt, wie eine visuelle Warnung im Ausnahmefall auszusehen hat.</li>
<li>Mit Hilfe von XForms können beim Absenden der Daten diese als XML an den Server übermitteln werden und daher ist diese Technik besonders für SOA interessant.</li>
<li>Arithmetische Berechnungen stehen sowohl im UI als auch im Model zur Verfügung.</li>
<li>Durch die Datenbindung zwischen Model und UI können eingegebene Daten automatisch aktualisiert werden (beispielsweise bei einer Warenliste wird der Endpreis automatisch berechnet und angezeigt, ohne dass sich der Programmierer oder der Anwender speziell um das Auslösen eines&Acirc;&nbsp; "neu berechnen" Events kümmern müsste).</li>
<li>Für Events und Actions (in HTML unter "onclick" usw. bekannt) wird nun einheitlich der <a href="http://www.w3.org/TR/xml-events" target="_blank">XML-Events</a> Standard genutzt und bietet so noch umfangreichere Möglichkeiten.</li>
<li>Durch "switching" ist eine teilweise Sichtbarkeit eines sehr umfangreichen Formulars oder das Einblenden ausschließlich für den Benutzer durch seine bisherigen Eingaben bedingten relevanten Eingabefelder möglich. Ein Formular muss somit nicht mehr über mehrere HTML-Seiten aufgeteilt werden, was bei herkömmlicher HTML-Technik zu Problemen mit der Speicherung von den temporär eingegebenen Daten führte.</li>
<li>Lokales Zwischenspeichern von Formulardaten ist in XML-Dateien (einer lokalen Instanz-Datei) möglich. Besonders für sehr mobile Dienste ist dies interessant, denen keine permanente Internetverbindung zur Verfügung steht.</li>
<li>Durch die verstärkte Clientbasierte Eingabelogik-Implementierungsmöglichkeiten sind erheblich weniger Serverzugriffe zu erwarten, was zu einer geringeren Auslastung der Bandbreite und auch des Servers führt. Ebenfalls sind Standalone Anwendungen ohne eines (Web)Servers denkbar, da die Nutzung von JavaScript&acirc;&bdquo;&cent; zur Implementation der Geschäftslogik möglich ist.</li><br />
</ul><br />
Insgesamt gesehen stellt XForms eine sehr interessante Technik bereit, die zu RIAs führt, welche fast vollständig ohne Scripting auskommen. Besonders in sicherheitsrelevanten Bereichen ist dieser Ansatz von hoher Prisanz. Auch die Optik muss dabei nicht zwangsweise leiden, da XForms zusammen mit SVG, CSS und SMIL einsetzt werden könnte. Diese Standards definieren grafische, visualisierende und dynamische Präsentations-Möglichkeiten. Mit der theoretischen Möglichkeit das XForms-Model zusammen mit proprietären Lösungen nutzen zu können, stünde auch MS Silverlight oder Flash zur Visualisierung der Daten mit der Power von XForms-Model zur Verfügung. Für diese Kombination gibt es derzeit aber keine oder zumindest nicht im Internet offensichtlich auffindbare Beispiele. Leider ist darüber hinaus der XForms Standard momentan noch in keinem gängigen Internetbrowser fester Bestandteil und muss als Browsererweiterung installiert werden. Diese Erweiterungen basieren oft auf JavaScript implementierungen des Standards und sind für fast alle Browser verfügbar.<br />
Hoffentlich wird dieser Standard bald fester Bestandteil jedes Browsers!</p>
<p>In der nächsten Folge werde ich Microsofts eigenen Ansatz XAML vorstellen.</p>
<p>(Das Copyright der Abbildung liegt beim w3c).</p>
