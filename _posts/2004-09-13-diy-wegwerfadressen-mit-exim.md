---
layout: post
title: DIY Wegwerfadressen mit Exim
created: 1095098878
---
> Eine Extension Adress spannt einen Namensraum unterhalb (oder hinter)
> eine normalen Adresse auf. Das sieht dann zum Beispiel so aus, daß es
> neben der Hauptadresse paul@example.com auch noch
> paul-irgendwas@example.com gibt. Das Trennzeichen kann genau genommen
> jedes beliebige im Localpart (der Teil vor dem @) erlaubte sein,
> üblich sind allerdings + und -.<cite>[o-y-d-t » Namespaces][]</cite>

Diese Adressen benutze ich selbst schon lange, allerdings nur zur
Kennzeichnung und zum automatischen Einsortieren.
 [Blacky][] geht den nächsten logischen Schritt weiter und beschreibt
[eine einfache Lösung][o-y-d-t » Namespaces], in der zulässige
Extensions in eine - vom Benutzer erstellte - Datei eingetragen werden.
Ist eine angeforderte Extension dort nicht eingetragen, wird gebounced,
ist sie vorhanden wird ganz normal ausgeliefert. Will also Paul nicht
mehr unter der Adresse paul-irgendwas erreichbar sein, so muss er nur
den Eintrag -irgendwas aus seiner Extensionsdatei entfernen. Feine
Sache.

 Jetzt muss ich nur meine ganzen Extensions zusammensuchen, die sich
über die letzten 2 Jahre angesammelt haben und hoffen, dass ich keine
übersehe…

  [o-y-d-t » Namespaces]: http://www.schwarzvogel.de/blog/index.php?p=275
  [Blacky]: http://www.schwarzvogel.de/blog
