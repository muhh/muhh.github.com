---
layout: post 
title: Shared Folder in VirtualBox
permalink: 
published: true
categories: [Drupal]
tags: [virtual box, web, ssh]
---

Wieso hat mir denn keiner gesagt, was für eine feine Sache "shared folders" in virtuellen Maschinen sind?

Vorher hab ich mich immer per SSH in die Maschine eingeloggt und lokal gearbeitet oder etwas fortgeschrittener über fuse das Verzeichnis auf dem Host eingebunden. Was aber immer recht instabil bzw. umständlich war.

So holt sich die VM die Projektverzeichnisse selbst und automatisch beim Booten rein. Auf dem Host kann ich die Dateien direkt bearbeiten und versionieren. Backup kann dann auch über die Bordmittel des Hosts erledigt werden.  
Außerdem spart es Platz in der VM, da sie diese Daten nicht mehr selbst speichern muss. Was auch wieder die Datensicherung dessen Systems vereinfacht und schlanker macht.

*Wundervoll*!

Nur die Datenbanken müssen noch sinnvoll da rausgeholt werden. Vielleicht funktioniert es ja auch gut, deren Verzeichnisse in diesen Shared Folder zu legen?