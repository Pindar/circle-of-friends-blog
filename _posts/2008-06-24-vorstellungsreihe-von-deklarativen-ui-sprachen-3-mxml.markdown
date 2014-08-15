---
layout: post
status: publish
published: true
title: " Vorstellungsreihe von deklarativen UI-Sprachen (3) MXML "
author:
  display_name: Pindar
  login: Pindar
  
  url: http://www.pindarsign.de
author_login: Pindar

author_url: http://www.pindarsign.de
excerpt: MXML ist eine deklarative User Interface Sprache von Adobe und ist Teil von
  Flex. Adobe Flex ist mehr an den Bedürfnissen eines Programmierers
  angepasst als Adobe Flash. Mit Flex, also mit MXML zusammen mit ActionScript 3,
  lassen sich "Rich Internet Applications" (RIAs) erstellen. Mit Hilfe von Adobe AIR
  sind erstellte RIAs nicht von einem Webbrowser abhängig, sondern
  benötigen nur die Laufzeitumgebung Adobe AIR am Clienten. Dies hat
  den Vorteil, dass diese Anwendungen sich tatsächlich wie Desktopanwendungen
  anfühlen und dieses auch sind, denn als AIR-Anwendung genießen
  diese RIAs das entscheidende Plus weitgehendere Rechte auch auf dem Client-Rechner
  zu besitzen, wie beispielsweise Dateien schreiben zu dürfen. Zur
  Sicherheit des Anwenders wird bei jeder "Installation" der Anwendung auf diese zusätzlichen
  Rechte hingewiesen und darüber hinaus sind Herkunftszertifikate notwendig.
  Doch können Flex Anwendungen auch zu "normalen" swf-Dateien kompiliert
  werden, welche vom weiter verbreiteten Adobe Flash Plug In ausgeführt
  werden können. Diese Anwendungen unterliegen dann allerdings den üblichen
  Restriktionen einer Flash-Webapplikation. Des weiteren bietet Flex eine gute Zusammenarbeit
  mit Adobe Flash, sodass die entstehenden Anwendungen von Grafikern und Programmieren
  sehr einfach erstellt werden können, ohne, dass sich ein Grafiker unbedingt
  mit Programmcode beschäftigen muss.
wordpress_id: 140
wordpress_url: http://www.pindarsign.de/webblog/?p=140
date: '2008-06-24 22:54:40 +0200'
date_gmt: '2008-06-24 20:54:40 +0200'
categories:
- Rich Internet Application
tags:
- xml
- ui
- mxml
- actionscript
- flex
comments: []
---
<p>MXML ist eine deklarative User Interface Sprache von Adobe und ist Teil von Flex. Adobe Flex ist mehr an den Bedürfnissen eines Programmierers angepasst als Adobe Flash. Mit Flex, also mit MXML zusammen mit ActionScript 3, lassen sich "Rich Internet Applications" (RIAs) erstellen. Mit Hilfe von Adobe AIR sind erstellte RIAs nicht von einem Webbrowser abhängig, sondern benötigen nur die Laufzeitumgebung Adobe AIR am Clienten. Dies hat den Vorteil, dass diese Anwendungen sich tatsächlich wie Desktopanwendungen anfühlen und dieses auch sind, denn als AIR-Anwendung genießen diese RIAs das entscheidende Plus weitgehendere Rechte auch auf dem Client-Rechner zu besitzen, wie beispielsweise Dateien schreiben zu dürfen. Zur Sicherheit des Anwenders wird bei jeder "Installation" der Anwendung auf diese zusätzlichen Rechte hingewiesen und darüber hinaus sind Herkunftszertifikate notwendig. Doch können Flex Anwendungen auch zu "normalen" swf-Dateien kompiliert werden, welche vom weiter verbreiteten Adobe Flash Plug In ausgeführt werden können. Diese Anwendungen unterliegen dann allerdings den üblichen Restriktionen einer Flash-Webapplikation. Des weiteren bietet Flex eine gute Zusammenarbeit mit Adobe Flash, sodass die entstehenden Anwendungen von Grafikern und Programmieren sehr einfach erstellt werden können, ohne, dass sich ein Grafiker unbedingt mit Programmcode beschäftigen muss.<a id="more"></a><a id="more-140"></a></p>
<h2>MXML Struktur und Nutzen</h2><br />
MXML selbst definiert die Benutzeroberfläche. Damit können sehr umfangreiche Eingabemasken einfach und schnell erstellt werden. Die Positionierung und das detaillierte Aussehen der einzelnen Objekte kann entweder zentral mit Hilfe von Cascading Style Sheets (CSS) definiert werden, oder einiges kann auch direkt mit Hilfe des MXML-Codes beschrieben werden. Insgesamt ist aber eine klare Trennung der Struktur der Tags und des Layouts möglich. Die MXML-Tags werden bei der Compilierung in ActionScript Objekte transformiert, sodass eine Anpassung der deklarativen Elemente möglich ist. Durch Vererbung der Originalklassen können neue MXML Tags auf Basis bestehender erstellt werden. Auch ganz neue MXML-Tags sind umsetzbar. Diese neuen Tags können in MXML via Namespaces eingebunden werden. Da aus ActionScript auch JavaScript-Funktionen der Host Sprache aufgerufen werden können, wäre es denkbar eine bestehende XForms JavaScript Implementierung dadurch relativ einfach in MXML zu integrieren. Der Nutzen bliebe jedoch im gering, da fast alle Funktionalitäten von XForms auch in MXML bereits verfügbar sind. Diverse Validierungsmöglichkeiten, auch deklarativ beschreibbar, sind in MXML verfügbar. Auch deklaratives Eventhandling ist möglich.</p>
<p>ActionScript nimmt darüber hinaus die Rolle des Code Behind ein. Mit Hilfe der OOP Sprache wird das Eventhandling der UI-Objekte realisiert und es kann zudem die Clientseitige Bussiness Logik umgesetzt werden. Auch die Auswertung der von Serverseite kommenden Daten wird mit ActionScript erledigt. Der Code kann entweder direkt in die MXML-Datei integriert werden oder er wird in eigene (wiederverwendbare) packages gekapselt und in die entsprechenden MXML-Dateien eingebunden.</p>
<p>Mit ECMAScript for XML (E4X) ist es zudem, ähnlich wie mit XPATH, möglich XML-Dokumente auszulesen und auch zu bearbeiten. E4X wurde umgesetzt, da XPath für zu Umfangreich und zu schwierig von den Flex Entwicklern angesehen wurde. Doch existiert eine XPath Erweiterung für MXML mit Hilfe derer man auch mit normalen XPath Anfragen arbeiten kann.</p>
<h2>Flex vs. Silverlight vs. XForms</h2><br />
Auf den ersten Blick unterscheidet sich Flexs MXML von Silverlights XAML nur sehr wenig. Beide deklarativen UI Sprachen haben für die meisten Objekte sogar die selben Namen. Doch sieht man auf den zweiten Blick, dass Flex aus dem Blickwinkel der Webentwickler kreiert wurde. MXML wird mit CSS layouted und ActionScript erinnert trotz dem ausgewachsenen OOP Status noch teilweise an eine Skriptsprache. Im Gegensatz dazu wartet Silverlight mit C# auf und lässt damit keinen Zweifel aufkommen, dass die Silverlightentwicklung von der Programmiertechnischen Sicht aus vorangetrieben wurde. Für Flex spricht jedoch die nahezu vollständige Verfügbarkeit eines Flashplayers auf ebenfalls fast allen elektronischen Eingabegeräten und die Möglichkeit ein fast natives Programm mittels Adobe AIR zu erstellen, bei welchem man sogar das Aussehen der Fenster selbst anpassen kann. Diese Fähigkeit bietet Silverlight nicht. Auch im Bereich Multimedia punktet Flex deutlich gegen seine Konkurrenz. Adobe unterstützt eine Reihe von Multimediaobjekten, wie H.264, MP3, flv, mov und weitere. WMV Dateien werden von Adobe nicht unterstützt, Silverlight hingegen unterstützt nur diese Dateiformatreihe. In fast allen übrigen Belangen sind sich beide Sprachen derart ähnlich, dass es beinahe schade ist in Silverlight kein ActionScript als Code Behind verwenden zu können, denn sonst könnte man beide Standards fast nahtlos ineinander überführen.</p>
<p>Ein Vergleich von Flex mit XForms verhält sich folgerichtig fast gleich mit dem Vergleich von Silverlight und XForms. Nur besitzt MXML bereits deklarative Validierungsmöglichkeiten. Hinzufügen möchte ich noch, dass es auch bei Silverlight (XAML) möglich ist selbst Tags zu definieren, wodurch in beiden Sprachen selbsterstellte, deklarative Elemente zur Datenvalidierung verfügbar gemacht werden können.</p>
<h2>Fazit und Entwicklungsunterstützung</h2><br />
Insgesamt ist Flex und die damit verbunden MXML Sprache sehr ausgewachsen, schnell verständlich und einfach lernbar und ebenso einfach erweiterbar. Die Integration von Flashanwendungen in Flex bietet weitere Vorteile. Zum einen müssen Grafiker keine neuen Tools erlernen und zum anderen vereinfacht dies auch die Zusammenarbeit von Grafikern und Programmierern. ActionScript selbst ist in Version 3 nun vollständig OOP Fähig und ein einarbeiten in die Sprache ist nicht sehr schwehr, was dem Entwickler zugute kommt.</p>
<p>Auch an Unterstützung in Form von HowTos, Webcasts, Foren, offizielen Dokumentationen, bereitgestellten Frameworks etc. mangelt es nicht im geringsten. Ein effizienter Einstieg ist auf jeden Fall gewährleistet. Dem Profientwickler greift Adobe zudem mit der kostenpflichtigen Flex Builder IDE unter die Arme. Diese basiert auf eclipse, wodurch sie auf allen gängigen Plattformen lauffähig ist (Windows, Macintosh, Linux) und bietet alle Funktionen die eine vernünftige IDE bieten muss.</p>
<p>Alles in allem kann ich diese Technologie nur weiterempfehlen.</p>
<p>In der nächsten Folge wird es um XUL, der UI-Sprache von Mozilla gehen.</p>
<h3>Weblinks</h3></p>
<ul>
<li>http://learn.adobe.com/wiki/display/Flex/Getting+Started</li>
<li>http://www.christianpfeil.com/</li>
<li>http://ajaxian.com/</li>
<li>http://livedocs.adobe.com/flex/3/html/help.html</li>
<li>http://labs.adobe.com/wiki/index.php/Cairngorm</li>
<li>http://www.riapedia.com/</li><br />
</ul></p>
