---
layout: post
status: publish
published: true
title: Debian &amp; EEE PC 901 acting like a charm!
author:
  display_name: Strahler
  login: Strahler
  
  url: http://
author_login: Strahler

author_url: http://
excerpt: "Sessen mitnander,\r\n\r\nendlich is es soweit und ich kann euch bisschen
  was zur Installation von Debian sid auf meinem EEE PC 901 erzählen.\r\n\r\nBin
  bisschen spät dran, aber mein Geburtstag kam mir noch dazwischen
  und nebenher flieg ich ja am Donnerstag nach Glasgow. ;)\r\n\r\nAaaaaaaalso,\r\n\r\nam
  Montag kam bereits der 2GB RAM-Riegel an und ich hab meinen kleinen am Dienstag,
  den 19.8. von Alternate geschickt bekommen."
wordpress_id: 238
wordpress_url: http://www.pindarsign.de/webblog/?p=238
date: '2008-08-26 18:16:53 +0200'
date_gmt: '2008-08-26 16:16:53 +0200'
categories:
- Technik
- Linux
tags:
- EEE PC 901
- Debian
- Sid
- KDE 3.5.9
comments:
- id: 4769
  author: Michi
  
  author_url: http://mesite.de/webblog
  date: '2008-08-28 13:26:31 +0200'
  date_gmt: '2008-08-28 11:26:31 +0200'
  content: "hey nettes spielzeug hast dir zugelegt.\r\nviel spaß in glasgow.\r\ngruß,
    michi"
- id: 34947
  author: dagobart
  
  author_url: http://dagobart.wordpress.com/2008/11/12/status-whats-up-with-my-computer-systems/
  date: '2008-11-15 20:05:53 +0100'
  date_gmt: '2008-11-15 19:05:53 +0100'
  content: "Hi,\r\n\r\nschönen Dank für den Erfahrungebericht.
    Habe mir auch gerade (endlich!;) einen E901 zugelegt &amp; schaue gerade 'n bisschen
    rum, wie man da wohl ein Debian drauf bekommt. Fürs Archiv will
    ich das Windows allerdings erstmal runterlesen. Schätze, das wird
    mit Damn Small Linux und dd irgendwie hinhauen.\r\n&nbsp;\r\n\r\nWährend
    des Lesens Deines Berichtes sind mir zwei Dinge aufgefallen, die vielleicht für
    Dich interessant/relevant sein könnten:\r\n\r\na) Wenn die eine
    SSD austauschbar ist, würde ich die Swap-Partition darauf machen.
    Da der zugrundeliegende Speicher = Flash ist, wird er irgendwann aufgrund zu vieler
    Schreibvorgänge verrecken. (~100.000, oder was die heute schaffen,
    sind viel -- aber für eine Swap-Partition? Eher nicht, oder?) --
    Da wäre vielleicht gut, wenn man den betroffenen Speicher anschließend
    austauschen könnte.\r\n\r\nb) In KDE-Applikationen kann man auch
    mit einem vertikalen Mausrad horizontal scrollen. Vielleicht suboptimal -- aber
    es geht halt. :) Indem man den Mauszeiger auf dem Scrollbar platziert und dann
    mit dem Rad herumrollt. Für Iceweasel geht das jedoch nicht.\r\n\r\nSo,
    mal weiter nach Links/Hinweisen zum Windows-Deinstallieren, Etch-/Lenny-Installieren
    suchen.\r\n\r\nWürd' mich über einen Besuch in meinem
    Blog freuen. ;-)"
- id: 35587
  author: Strahler
  
  author_url: http://
  date: '2008-11-16 17:34:07 +0100'
  date_gmt: '2008-11-16 16:34:07 +0100'
  content: "Hi dagobart,\r\n\r\ndanke für das positive Feedback!\r\n\r\nIch
    bin mir sicher du bist schon über die Seite gestolpert: http://wiki.debian.org/DebianEeePC/\r\n\r\nHier
    ist alles beschrieben was du zur Installation wissen musst. Mittlerweile sind
    auch die acpi Skripten und der Installer besser und weiter als \"damals\" noch
    bei mir. ;) - Es funktioniert nun alles out of the box. Nut Bluetooth lässt
    sich über die Sondertasten noch nicht steuern. Wenn es im Bios
    \ aktiviert ist, ist es immer an.\r\n\r\nMit der Swap-Partition:\r\nZur Lebenszeit
    der SSD ist dieser Bericht sehr interessant:\r\nhttp://wiki.eeeuser.com/ssd_write_limit\r\n\r\nIch
    gebe dir vollkommen recht. Eigentlich wollte ich das ganze umdrehen. Also /home
    und /swap auf die austauschbare SSD und das System auf die fest installierte.
    Ich bin im moment aber für ein Jahr in Schottland und habe somit
    meinen eeePC als einzigen Computer dabei. Somit wollte ich sicher gehen, dass
    wenn ich doch noch einiges an Programme installieren muss, mir der Platz auf /root
    nicht ausgeht.\r\nAn sich ist mir das Problem mit der Swap-Partition bewusst,
    deshalb habe ich das \"swapping\" ausgestellt. Ich habe die Swap-Partition zwar
    angelegt um hibernate nutzen zu können, aber ich lasse den Kernel
    nicht darauf temporär auslagern. \r\nDas sollte die SSD dann doch
    etwas schonen.\r\n\r\nZum horizontal-scrollen:\r\nEs wäre ganz
    witzig, das gebe ich zu. Im Moment fehlt es mir aber nicht wirklich. Aber im 2.6.28
    Kernel soll ein neuer Treiber für das eeePC Synaptic-Touchpad enthalten
    sein, der das horizontale scrolling unterstützen soll. Ich bin
    mal gespannt. \r\nAnsonsten danke für den Tipp!\r\n\r\nDann wünsche
    ich dir viel Erfolg beim Windows sichern und viel mehr erfolg beim Debian installieren!
    ;)\r\n\r\nViele Grüße aus Glasgow\r\nStrahler"
- id: 37923
  author: dagobart
  
  author_url: http://dagobart.wordpress.com/
  date: '2008-12-03 19:02:00 +0100'
  date_gmt: '2008-12-03 18:02:00 +0100'
  content: "Hi Strahler,\r\n\r\nsorry, habe Deine Antwort erst gerade im Akismet-Spam
    gefunden. Ist jetzt freigeschaltet.\r\n\r\nMein Eee901 läuft inzwischen
    fröhlich vor sich hin. Habe irgendwo eine 2GB-SD-Karte für
    5 Euro aufgelesen und als Swap eingerichtet (1 Partition), wurde aber bisher nicht
    genutzt. Der Hauptspeicher scheint wohl zu reichen.\r\n\r\nDas Hibernating scheint
    nicht sauber zu funktionieren, bzw. das Aufwachen. Ich bin noch nicht ganz dahinter
    gekommen, ob es an meinem ungeduldigen Auf-der-Tastatur-Rumklimpern gelegen hat,
    oder ob da Aufwachen regulär <b>nach drei Minuten</b> zuende
    ist. -- Hab's abeschaltet. Normales Neustarten ist schneller.\r\n\r\nBye,\r\ndagobart"
- id: 39742
  author: Strahler
  
  author_url: http://
  date: '2008-12-22 13:32:40 +0100'
  date_gmt: '2008-12-22 12:32:40 +0100'
  content: |-
    Hi dagobart,

    sorry, ich bin 2 Wochen von Nordengland nach Südengland gewandert und hab dann noch gleich Irland mitgenommen. ;)

    Freut mich, dass dein 901er fröhllich mit Debian läuft. :-)
    Das ist mein letztes Problem. Mein 901er wacht manchmal ausm Suspend-to-Ram und -Disk auch nicht auf....
    Keine Ahnung ob das am uswsusp Packet liegt oder am Kernel (mit 2.6.28 soll ja alles besser werden)... aber es ist sehr, sehr ärgerlich!
    Sollest du eine Lösung finden würde es mich freuen wenn du sie mir mitteilen könntest. ;)

    Gruß
    Strahler
- id: 39756
  author: Strahler
  
  author_url: ''
  date: '2009-01-16 16:17:18 +0100'
  date_gmt: '2009-01-16 15:17:18 +0100'
  content: "Hi dagobart,\r\nich nochmal. Wegen Hibernate / suspend.\r\n\r\nIch
    habe vor ca 4. Wochen nochmal dpkg-reconfigure uswsusp durchgeführt.
    \r\nHabe allerdings die maximale Image size (nicht wie default die größe
    der Swap-Partition) auf 0 gestellt. Das heißt er versucht das Image
    so klein wie möglich zu gestalten. \r\nSeitdem funktioniert suspend2ram
    und suspend2disk einwandfrei. \r\nAuch wenn ich ihn mal 4h im s2ram lasse ist
    der Akkuverbrauch minimal.\r\n\r\nGruß\r\nStrahler"
- id: 39757
  author: dagobart
  
  author_url: http://dagobart.wordpress.com/
  date: '2009-01-17 20:13:47 +0100'
  date_gmt: '2009-01-17 19:13:47 +0100'
  content: "Habe gleich mal probiert, ob ich das auch so hinbekomme. Leider nicht.
    Bleibt bei den drei Minuten; habe es wieder danach abgebrochen (und hatte hinterher
    ensprechend viele ungültige INodes).\r\n\r\nAber ist nicht wild:
    Suspend to RAM funktioniert wunderbar, auch über zig Stunden hinweg.
    Genau wie Du sagst.\r\n\r\nDanke für Deinen Kommentar auf meinem
    Blog."
- id: 39851
  author: Cordy
  
  author_url: http://www.google.com/
  date: '2011-07-08 03:25:03 +0200'
  date_gmt: '2011-07-08 01:25:03 +0200'
  content: Ab fab my golody man.
---
<p>Sessen mitnander,</p>
<p>endlich is es soweit und ich kann euch bisschen was zur Installation von Debian sid auf meinem EEE PC 901 erzählen.</p>
<p>Bin bisschen spät dran, aber mein Geburtstag kam mir noch dazwischen und nebenher flieg ich ja am Donnerstag nach Glasgow. ;)</p>
<p>Aaaaaaaalso,</p>
<p>am Montag kam bereits der 2GB RAM-Riegel an und ich hab meinen kleinen am Dienstag, den 19.8. von Alternate geschickt bekommen.<a id="more"></a><a id="more-238"></a></p>
<p>Erstmal auspacken:</p>
<p>[caption id="attachment_239" align="alignnone" width="300" caption="Schachtel mit RAM"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00305.jpg"><img class="size-medium wp-image-239" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00305-300x225.jpg" alt="Schachtel mit RAM" width="300" height="225" /></a>[/caption]</p>
<p>Ein weiteres Foto zeigt das Zubehör (Handbuch, Ladegerät, Akku und ein Displayreinigungstuch). Leider hab ich vergessen die kleine Tragetasche ins Foto zu rücken... Sie is schwarz und es steht Asus und eeePC drauf. ;)</p>
<p>[caption id="attachment_240" align="alignnone" width="300" caption="EEE PC 901 mit Zubehör"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00306.jpg"><img class="size-medium wp-image-240" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00306-300x225.jpg" alt="EEE PC 901 mit Zubehör" width="300" height="225" /></a>[/caption]</p>
<p>Ich gebe zu, ich hab dann doch mal das vorinstallierte Windows XP Home hochgefahren um zu sehen ob denn auch alles funktioniert...</p>
<p>[caption id="attachment_241" align="alignnone" width="300" caption="WinXP@Home"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00307.jpg"><img class="size-medium wp-image-241" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00307-300x225.jpg" alt="WinXP@Home" width="300" height="225" /></a>[/caption]</p>
<p>Aaaaalles klar. Windows... gesehen, gelacht, gelöscht.</p>
<p>Was haben Windows und ein U-Boot gemeinsam? Wenn man ein Fenster auf macht, gehen die Probleme los...</p>
<p>Linux is like a Wigwam: No windows, no gates and an apache inside....</p>
<p>Jaja, wir kennen es alle. ;)</p>
<p>Also, USB-Stick formatiert und das Debian-EEEPC-Image installiert.</p>
<p>Danach den EEEPC neu gebootet und schon hatte ich den guten, bekannten Debian Installer vor mir.</p>
<p>Ich habe mich dann aufgrund der doch etwas schwächeren Leistung der CPU und SSD gegen eine komplette Verschlüsselung des Systems entschieden. Außerdem bei dem Speicherplatz Angebot, kann man garned so viel wichtige Sachen draufbringen. ;)</p>
<p>[caption id="attachment_242" align="alignnone" width="300" caption="Debian Installer"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00309.jpg"><img class="size-medium wp-image-242" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00309-300x225.jpg" alt="Debian Installer" width="300" height="225" /></a>[/caption]</p>
<p>[caption id="attachment_243" align="alignnone" width="300" caption="Grundsystem"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00310.jpg"><img class="size-medium wp-image-243" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00310-300x225.jpg" alt="Grundsystem" width="300" height="225" /></a>[/caption]</p>
<p>.... dann muss ich gestehen, nachdem ich dich schon seit längerem kein Debian mehr aufgesetzt habe, musste ich mal wieder bisschen Lehrgeld / Lehrzeit zahlen... nein, Desktop-Environement zu beginn aufsetzen ist nictht sehr sinnvoll... jaaaaa... ich erspar' euch die Einzelheiten.</p>
<p>Wie gesagt ist eine 4GB SSD fest eingebaut und eine zweite, austauschbare 8GB SSD drin.</p>
<p>Ich habe die 8GB als /root eingerichtet um viele Programme installieren / ausprobieren zu können. Die 4GB SSD wurde in eine 3GB /home und 1GB Swap paritioniert.</p>
<p>Dazu habe ich mir noch ein externes Gehäuse bestellt und eine Festplatte mit 500GB aus meinem Desktop ausgebaut. Diese werde ich als Datenspeicher für meinen EEE PC verwenden.</p>
<p>Nach kurzer Zeit sah das Ganze dann so aus:</p>
<p>[caption id="attachment_244" align="alignnone" width="300" caption="Welcome to Debian@Guybrush"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00311.jpg"><img class="size-medium wp-image-244" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00311-300x225.jpg" alt="Welcome to Debian@Guybrush" width="300" height="225" /></a>[/caption]</p>
<p>Anschließend ging's an die Konfiguration des Systems... jaaa... des zieht sich immer a bissal aber ich kann heute sagen:</p>
<p>Es funktioniert:</p>
<p>Hotbuttons für:</p>
<p>- Mute Sound</p>
<p>- Volume up / down</p>
<p>- Wlan on / off</p>
<p>- Brightness up / down</p>
<p>- Webcam</p>
<p>- Go to Sleep</p>
<p>Ansonsten funktioniert: Suspend / Hibernate, also beim Zuklappen des Displaydeckels geht der Lappi in Suspend2Ram und ich kann ich auch in Suspend2Disk versetzen.</p>
<p>Es funktioniert auch das dynamische hoch und runtertakten der CPU.</p>
<p>Besonders hervorheben möchte ich die ca 5,5h Akkulaufzeit ohne Wlan sowie die Microphones an der Frontseite des Displays. Diese haben wirklich eine sehr gute Aufnahmequalität.</p>
<p>Bluetooth muss leider noch über einen Kommandozeilenaufruf aktiviert werden, dürfte aber nicht mehr lange dauern, bis das ebenfalls mit dem zugehörigen Hotbutton funzt.</p>
<p>[caption id="attachment_247" align="alignright" width="300" caption="Wlan surfing"]<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00317.jpg"><img class="size-medium wp-image-247" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00317-300x225.jpg" alt="Wlan surfing" width="300" height="225" /></a>[/caption]</p>
<p><a href="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00314.jpg"><img class="size-medium wp-image-246" src="http://www.pindarsign.de/webblog/wp-content/uploads/2008/08/dsc00314-300x225.jpg" alt="Debian Sid, KDE 3.5.9" width="300" height="225" /></a></p>
<div class="mceTemp">
<dl>
<dd>Debian Sid, KDE 3.5.9</dd> </dl></div><br />
Sorry, die Fotos sind teilweise etwas unscharf.</p>
<p>Was gibt es sonst noch zu erwähnen?</p>
<p>Es ist ein Multitouch-Touchpad verbaut. Vertikales scrollen funktioniert, der Mittelklick auch. Leider ist zoomen oder horizontales scrollen noch nicht unterstützt. Ich habe aber gelesen, dass im aktuell entwickelten 2.6.27er Kernel, ein Treiber für die Multitouch-Touchpads von Apple aufgenommen wurde. Da hier der gleiche Hersteller verwendet wird, bin ich mal recht zuversichtlich.</p>
<p>Die Tastatur ist wirklich etwas gewöhnungsbedürftig, aber was will man bei 9" erwarten und mit etwas Übung wird es auch nach und nach besser.</p>
<p>Eigentlich hätte ich gerne KDE 4.1 installiert, musste zu meiner eigenen Überraschung feststellen, dass in Debian sid immer noch KDE 3.5.9 ist (Drüfte wohl auch mit dem Freeze von Lenny zusammenhängen). Dazu habe ich gelesen, dass wenn man KDE 4.1 über die experimental Pakete installiert, man immer noch einiges manuell nachinstallieren / entfernen muss... und das is mir dann doch zu aufwändig gewesen.</p>
<p>Ich hab jetzt ehrlich gesagt nicht nachgewogen, aber die angegeben 1,1kg kommen meiner Meinung nach schon sehr gut hin.</p>
<p>Die Bootzeit bis zum Login-Screen liegt bei ca 15sec und das matte Display hat eine gute Helligkeit.</p>
<p>Recht viel mehr fällt mir jetzt nicht mehr ein, außer ich hab den kleinen jetzt schon gern. ;)</p>
<p>Gut, gut, dann geh ich mal Koffer packen.</p>
<p>Ich wünsch' allen Lernenden viel Erfolg dabei und bei den Prüfungen!</p>
<p>Viele Grüße</p>
<p>Strahler</p>
