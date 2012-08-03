---
layout: post
title: mailbloggen (mit Drupal)
created: 1082317295
---
Wenn das hier durchkommt, dann funktioniert [Drupals][] [mailhandler][]
Modul und ich muss mir nie mehr meine eigene Seite ansehen.

 [Wie funktioniert es?][]

Man schicke eine Mail an mailio-äd-byzero.de, wobei im From: dieselbe
Emailadresse stehen muss, wie sie auch für den Drupaluser eingetragen
ist.

Im restlichen Mailbody (nach einer leeren Zeile) folgt jetzt der
eigentliche Blogeintrag. Es wird nur der plain/text Teil einer Mail
ausgewertet, HTML Teile werden ignoriert. HTML im Eintrag ist leider im
Moment auch nicht möglich. Das Subject: ergibt den Titel für den
Blogeintrag.
 Der Body der Email selbst ist zweigeteilt.

Zuerst der “Commands” Abschnitt. Hier können Befehle an Drupals
Nodesystem übergeben werden. Eine kleine Kurzübersicht:

    pass: passwort

Um die Sicherheit ein wenig zu erhöhen, ist es notwendig hier das
Passwort des im Absender angegebenen Accounts einzutragen.

    type: blog

gibt den Nodetyp an. Im Moment gibt es hier nur blog.
 Dieser Befehl wird immer automatisch ausgeführt und ist deshalb in der
Mail nicht notwendig.

    taxonomy: [Kategorien]

Hier trägt mein ein, in welchen Kategorien (drupal: taxonomies) der
Eintrag gelistet werden soll. Hier können auch mehrere durch Komma
getrennte Kategorien stehen.

    promote: (0/1)

steuert, ob der Eintrag auf der [Titelseite][] angezeigt werden soll.
 0 für nein und 1 für ja.
 Bei 0 taucht der Eintrag nur im persönlichen Blog auf, allerdings immer
noch in der “Blogs” Box in der rechten Spalte. Dieser Befehl kann nur
ausgewertet werden, wenn der Benutzer speziellen Verwaltungszugriff hat.
Das bin aber eigentlich nur ich.

    status: (0/1)

setzt den “published” Parameter. 0 ergibt einen Draft, 1 veröffentlich
den Eintrag und er taucht im Blog auf.

    comment: (0/1/2)

gibt an, ob der Eintrag kommentiert werden kann. 0 für Deaktiviert, 1
für Nur-Lesen, 2 für Lesen und Schreiben.

Im restlichen Mailbody (nach einer leeren Zeile) folgt jetzt der
eigentliche Blogeintrag. Es wird nur der text/plain MIME-Part einer Mail
ausgewertet, HTML Teile werden ignoriert. HTML im Eintrag ist leider im
Moment auch nicht möglich. Vielleicht ist das die erste sinnvolle
Anwendung für HTML-Mails?

Signaturen werden abgeschnitten, allerdings nur, wenn diese mit “—”
eingeleitet sind. Outlook interessiert das wieder mal bestimmt nen
feuchten Dreck :-/

Die Mail, die diesen Eintrag auslösen würde, sieht dann vereinfacht so
aus:

    From: Markus Heurung <muhh@byzero.de>
    Subject: mailbloggen

    pass: ***
    taxonomy: [geek,technisch]
    comment: 2

    Wenn das hier durchkommt, dann funktioniert Drupals mailhandler Modul und
    ich muss mir nie mehr meine eigene Seite ansehen.

    Wie funktioniert es?

    Man schicke eine Mail an mailio-äd-byzero.de, wobei im From: dieselbe
    Emailadresse stehen muss, wie sie auch für den Drupaluser eingetragen
    ist.

    usw.

Das ist aber noch nicht alles…

Im Header lässt sich mittels eines speziell formatierten In-Reply-To:
auch die genaue “Position” des Posts angeben (geht auch mit dem Befehl
nid: im Commands Abschnitt der Mail)

    In-Reply-To: nid=5

würde zum Beispiel den Node mit der Nummer 5 editieren!

Im Zusammenspiel mit der Message-Id - diese wird auch ausgewertet -
ergeben sich hier geniale Möglichkeiten, wie zB. Kommentieren und
Antworten auf Kommentare von Posts, wodurch man im Prinzip eine
komplette Mail\<-\>WWW Schnittstelle zur Verfügung hat.

 Wie das allerdings genau funktioniert, muss ich erst noch selbst
herausfinden…


  [Drupals]: http://drupal.org
  [mailhandler]: http://drupal.org/project/mailhandler
  [Wie funktioniert es?]: blog/mailbloggen-mit-drupal
  [Titelseite]: http://byzero.de
