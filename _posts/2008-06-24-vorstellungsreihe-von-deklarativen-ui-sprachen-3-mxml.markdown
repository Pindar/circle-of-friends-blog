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
  Flex. Adobe Flex ist mehr an den Bed&Atilde;&frac14;rfnissen eines Programmierers
  angepasst als Adobe Flash. Mit Flex, also mit MXML zusammen mit ActionScript 3,
  lassen sich "Rich Internet Applications" (RIAs) erstellen. Mit Hilfe von Adobe AIR
  sind erstellte RIAs nicht von einem Webbrowser abh&Atilde;&curren;ngig, sondern
  ben&Atilde;&para;tigen nur die Laufzeitumgebung Adobe AIR am Clienten. Dies hat
  den Vorteil, dass diese Anwendungen sich tats&Atilde;&curren;chlich wie Desktopanwendungen
  anf&Atilde;&frac14;hlen und dieses auch sind, denn als AIR-Anwendung genie&Atilde;&Yuml;en
  diese RIAs das entscheidende Plus weitgehendere Rechte auch auf dem Client-Rechner
  zu besitzen, wie beispielsweise Dateien schreiben zu d&Atilde;&frac14;rfen. Zur
  Sicherheit des Anwenders wird bei jeder "Installation" der Anwendung auf diese zus&Atilde;&curren;tzlichen
  Rechte hingewiesen und dar&Atilde;&frac14;ber hinaus sind Herkunftszertifikate notwendig.
  Doch k&Atilde;&para;nnen Flex Anwendungen auch zu "normalen" swf-Dateien kompiliert
  werden, welche vom weiter verbreiteten Adobe Flash Plug In ausgef&Atilde;&frac14;hrt
  werden k&Atilde;&para;nnen. Diese Anwendungen unterliegen dann allerdings den &Atilde;&frac14;blichen
  Restriktionen einer Flash-Webapplikation. Des weiteren bietet Flex eine gute Zusammenarbeit
  mit Adobe Flash, sodass die entstehenden Anwendungen von Grafikern und Programmieren
  sehr einfach erstellt werden k&Atilde;&para;nnen, ohne, dass sich ein Grafiker unbedingt
  mit Programmcode besch&Atilde;&curren;ftigen muss.
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
<p>MXML ist eine deklarative User Interface Sprache von Adobe und ist Teil von Flex. Adobe Flex ist mehr an den Bed&Atilde;&frac14;rfnissen eines Programmierers angepasst als Adobe Flash. Mit Flex, also mit MXML zusammen mit ActionScript 3, lassen sich "Rich Internet Applications" (RIAs) erstellen. Mit Hilfe von Adobe AIR sind erstellte RIAs nicht von einem Webbrowser abh&Atilde;&curren;ngig, sondern ben&Atilde;&para;tigen nur die Laufzeitumgebung Adobe AIR am Clienten. Dies hat den Vorteil, dass diese Anwendungen sich tats&Atilde;&curren;chlich wie Desktopanwendungen anf&Atilde;&frac14;hlen und dieses auch sind, denn als AIR-Anwendung genie&Atilde;&Yuml;en diese RIAs das entscheidende Plus weitgehendere Rechte auch auf dem Client-Rechner zu besitzen, wie beispielsweise Dateien schreiben zu d&Atilde;&frac14;rfen. Zur Sicherheit des Anwenders wird bei jeder "Installation" der Anwendung auf diese zus&Atilde;&curren;tzlichen Rechte hingewiesen und dar&Atilde;&frac14;ber hinaus sind Herkunftszertifikate notwendig. Doch k&Atilde;&para;nnen Flex Anwendungen auch zu "normalen" swf-Dateien kompiliert werden, welche vom weiter verbreiteten Adobe Flash Plug In ausgef&Atilde;&frac14;hrt werden k&Atilde;&para;nnen. Diese Anwendungen unterliegen dann allerdings den &Atilde;&frac14;blichen Restriktionen einer Flash-Webapplikation. Des weiteren bietet Flex eine gute Zusammenarbeit mit Adobe Flash, sodass die entstehenden Anwendungen von Grafikern und Programmieren sehr einfach erstellt werden k&Atilde;&para;nnen, ohne, dass sich ein Grafiker unbedingt mit Programmcode besch&Atilde;&curren;ftigen muss.<a id="more"></a><a id="more-140"></a></p>
<h2>MXML Struktur und Nutzen<&#47;h2><br />
MXML selbst definiert die Benutzeroberfl&Atilde;&curren;che. Damit k&Atilde;&para;nnen sehr umfangreiche Eingabemasken einfach und schnell erstellt werden. Die Positionierung und das detaillierte Aussehen der einzelnen Objekte kann entweder zentral mit Hilfe von Cascading Style Sheets (CSS) definiert werden, oder einiges kann auch direkt mit Hilfe des MXML-Codes beschrieben werden. Insgesamt ist aber eine klare Trennung der Struktur der Tags und des Layouts m&Atilde;&para;glich. Die MXML-Tags werden bei der Compilierung in ActionScript Objekte transformiert, sodass eine Anpassung der deklarativen Elemente m&Atilde;&para;glich ist. Durch Vererbung der Originalklassen k&Atilde;&para;nnen neue MXML Tags auf Basis bestehender erstellt werden. Auch ganz neue MXML-Tags sind umsetzbar. Diese neuen Tags k&Atilde;&para;nnen in MXML via Namespaces eingebunden werden. Da aus ActionScript auch JavaScript-Funktionen der Host Sprache aufgerufen werden k&Atilde;&para;nnen, w&Atilde;&curren;re es denkbar eine bestehende XForms JavaScript Implementierung dadurch relativ einfach in MXML zu integrieren. Der Nutzen bliebe jedoch im gering, da fast alle Funktionalit&Atilde;&curren;ten von XForms auch in MXML bereits verf&Atilde;&frac14;gbar sind. Diverse Validierungsm&Atilde;&para;glichkeiten, auch deklarativ beschreibbar, sind in MXML verf&Atilde;&frac14;gbar. Auch deklaratives Eventhandling ist m&Atilde;&para;glich.</p>
<p>ActionScript nimmt dar&Atilde;&frac14;ber hinaus die Rolle des Code Behind ein. Mit Hilfe der OOP Sprache wird das Eventhandling der UI-Objekte realisiert und es kann zudem die Clientseitige Bussiness Logik umgesetzt werden. Auch die Auswertung der von Serverseite kommenden Daten wird mit ActionScript erledigt. Der Code kann entweder direkt in die MXML-Datei integriert werden oder er wird in eigene (wiederverwendbare) packages gekapselt und in die entsprechenden MXML-Dateien eingebunden.</p>
<p>Mit ECMAScript for XML (E4X) ist es zudem, &Atilde;&curren;hnlich wie mit XPATH, m&Atilde;&para;glich XML-Dokumente auszulesen und auch zu bearbeiten. E4X wurde umgesetzt, da XPath f&Atilde;&frac14;r zu Umfangreich und zu schwierig von den Flex Entwicklern angesehen wurde. Doch existiert eine XPath Erweiterung f&Atilde;&frac14;r MXML mit Hilfe derer man auch mit normalen XPath Anfragen arbeiten kann.</p>
<h2>Flex vs. Silverlight vs. XForms<&#47;h2><br />
Auf den ersten Blick unterscheidet sich Flexs MXML von Silverlights XAML nur sehr wenig. Beide deklarativen UI Sprachen haben f&Atilde;&frac14;r die meisten Objekte sogar die selben Namen. Doch sieht man auf den zweiten Blick, dass Flex aus dem Blickwinkel der Webentwickler kreiert wurde. MXML wird mit CSS layouted und ActionScript erinnert trotz dem ausgewachsenen OOP Status noch teilweise an eine Skriptsprache. Im Gegensatz dazu wartet Silverlight mit C# auf und l&Atilde;&curren;sst damit keinen Zweifel aufkommen, dass die Silverlightentwicklung von der Programmiertechnischen Sicht aus vorangetrieben wurde. F&Atilde;&frac14;r Flex spricht jedoch die nahezu vollst&Atilde;&curren;ndige Verf&Atilde;&frac14;gbarkeit eines Flashplayers auf ebenfalls fast allen elektronischen Eingabeger&Atilde;&curren;ten und die M&Atilde;&para;glichkeit ein fast natives Programm mittels Adobe AIR zu erstellen, bei welchem man sogar das Aussehen der Fenster selbst anpassen kann. Diese F&Atilde;&curren;higkeit bietet Silverlight nicht. Auch im Bereich Multimedia punktet Flex deutlich gegen seine Konkurrenz. Adobe unterst&Atilde;&frac14;tzt eine Reihe von Multimediaobjekten, wie H.264, MP3, flv, mov und weitere. WMV Dateien werden von Adobe nicht unterst&Atilde;&frac14;tzt, Silverlight hingegen unterst&Atilde;&frac14;tzt nur diese Dateiformatreihe. In fast allen &Atilde;&frac14;brigen Belangen sind sich beide Sprachen derart &Atilde;&curren;hnlich, dass es beinahe schade ist in Silverlight kein ActionScript als Code Behind verwenden zu k&Atilde;&para;nnen, denn sonst k&Atilde;&para;nnte man beide Standards fast nahtlos ineinander &Atilde;&frac14;berf&Atilde;&frac14;hren.</p>
<p>Ein Vergleich von Flex mit XForms verh&Atilde;&curren;lt sich folgerichtig fast gleich mit dem Vergleich von Silverlight und XForms. Nur besitzt MXML bereits deklarative Validierungsm&Atilde;&para;glichkeiten. Hinzuf&Atilde;&frac14;gen m&Atilde;&para;chte ich noch, dass es auch bei Silverlight (XAML) m&Atilde;&para;glich ist selbst Tags zu definieren, wodurch in beiden Sprachen selbsterstellte, deklarative Elemente zur Datenvalidierung verf&Atilde;&frac14;gbar gemacht werden k&Atilde;&para;nnen.</p>
<h2>Fazit und Entwicklungsunterst&Atilde;&frac14;tzung<&#47;h2><br />
Insgesamt ist Flex und die damit verbunden MXML Sprache sehr ausgewachsen, schnell verst&Atilde;&curren;ndlich und einfach lernbar und ebenso einfach erweiterbar. Die Integration von Flashanwendungen in Flex bietet weitere Vorteile. Zum einen m&Atilde;&frac14;ssen Grafiker keine neuen Tools erlernen und zum anderen vereinfacht dies auch die Zusammenarbeit von Grafikern und Programmierern. ActionScript selbst ist in Version 3 nun vollst&Atilde;&curren;ndig OOP F&Atilde;&curren;hig und ein einarbeiten in die Sprache ist nicht sehr schwehr, was dem Entwickler zugute kommt.</p>
<p>Auch an Unterst&Atilde;&frac14;tzung in Form von HowTos, Webcasts, Foren, offizielen Dokumentationen, bereitgestellten Frameworks etc. mangelt es nicht im geringsten. Ein effizienter Einstieg ist auf jeden Fall gew&Atilde;&curren;hrleistet. Dem Profientwickler greift Adobe zudem mit der kostenpflichtigen Flex Builder IDE unter die Arme. Diese basiert auf eclipse, wodurch sie auf allen g&Atilde;&curren;ngigen Plattformen lauff&Atilde;&curren;hig ist (Windows, Macintosh, Linux) und bietet alle Funktionen die eine vern&Atilde;&frac14;nftige IDE bieten muss.</p>
<p>Alles in allem kann ich diese Technologie nur weiterempfehlen.</p>
<p>In der n&Atilde;&curren;chsten Folge wird es um XUL, der UI-Sprache von Mozilla gehen.</p>
<h3>Weblinks<&#47;h3></p>
<ul>
<li>http:&#47;&#47;learn.adobe.com&#47;wiki&#47;display&#47;Flex&#47;Getting+Started<&#47;li>
<li>http:&#47;&#47;www.christianpfeil.com&#47;<&#47;li>
<li>http:&#47;&#47;ajaxian.com&#47;<&#47;li>
<li>http:&#47;&#47;livedocs.adobe.com&#47;flex&#47;3&#47;html&#47;help.html<&#47;li>
<li>http:&#47;&#47;labs.adobe.com&#47;wiki&#47;index.php&#47;Cairngorm<&#47;li>
<li>http:&#47;&#47;www.riapedia.com&#47;<&#47;li><br />
<&#47;ul></p>
