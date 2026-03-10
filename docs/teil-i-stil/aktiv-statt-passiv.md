# Sag, wer handelt.

**TL;DR:** Das Passiv versteckt den Handelnden. Das Aktiv zeigt ihn. Schreib aktiv, es sei denn, der Handelnde ist unwichtig oder unbekannt.

---

## Warum

Ein Satz braucht einen Akteur. Jemanden, der etwas tut. Das Passiv nimmt diesen Akteur heraus. Es verschleiert, wer verantwortlich ist. Es macht Sätze länger. Es macht sie schwerer.

Wolf Schneider nannte das Passiv die "hässlichste Form des Verbs". Das stimmt nicht immer. Aber meistens stimmt es.

Das Passiv ist das Lieblingsverb der Bürokratie. Behörden schreiben passiv, weil niemand verantwortlich sein will. Unternehmen schreiben passiv, weil es seriös klingt. Beides ist falsch. Seriös klingt, wer klar sagt, was er tut.

---

## Der Diff

<div class="diff-grid" markdown>
!!! vorher "Vorher"
    Die Einstellungen müssen vom Nutzer gespeichert werden.

!!! nachher "Nachher"
    Speichere deine Einstellungen.
</div>

Der erste Satz hat neun Wörter. Der zweite hat drei. Der erste versteckt den Nutzer hinter "vom Nutzer". Der zweite spricht ihn an.

<div class="diff-grid" markdown>
!!! vorher "Vorher"
    Es wurde beschlossen, die Frist zu verlängern.

!!! nachher "Nachher"
    Der Vorstand verlängerte die Frist.
</div>

Wer beschloss? Im Passiv weiß es niemand. Im Aktiv steht es da.

<div class="diff-grid" markdown>
!!! vorher "Vorher"
    Die Seite kann über den Button oben rechts aufgerufen werden.

!!! nachher "Nachher"
    Klicke oben rechts auf Seite öffnen.
</div>

<div class="diff-grid" markdown>
!!! vorher "Vorher"
    Im Rahmen der Qualitätssicherung wurde festgestellt, dass Verbesserungsbedarf besteht.

!!! nachher "Nachher"
    Wir prüften die Qualität. Sie reicht nicht.
</div>

Zwei Sätze statt einem. Kürzer. Klarer. Und plötzlich gibt es ein "Wir", das Verantwortung übernimmt.

---

## Die Mechanik

Passiv erkennen ist einfach. Suche nach diesen Mustern:

- "wird" + Partizip: *wird gespeichert, wird geprüft, wird durchgeführt*
- "wurde" + Partizip: *wurde beschlossen, wurde festgestellt*
- "ist" + "zu" + Infinitiv: *ist zu beachten, ist durchzuführen*
- "lässt sich": *lässt sich feststellen, lässt sich sagen*
- "man": *man sollte, man kann, man muss* (kein grammatisches Passiv, aber es versteckt den Akteur genauso)

Aktiv machen ist auch einfach. Stelle zwei Fragen:

1. **Wer handelt?** Wenn die Antwort fehlt, füge sie hinzu.
2. **Was tut diese Person?** Das Verb kommt nach vorn.

Aus "Die Daten werden verarbeitet" wird: Wer verarbeitet? Das System. Also: "Das System verarbeitet die Daten."

Aus "Es ist zu beachten, dass" wird: Wer beachtet? Du. Also: "Beachte, dass."

---

## Ausnahmen

Nicht jedes Passiv ist schlecht. Manchmal ist der Handelnde unwichtig.

"Das Gebäude wurde 1923 errichtet." Wer es errichtete, spielt keine Rolle. Das Passiv ist hier richtig.

"Die E-Mail wurde zugestellt." Der Mailserver ist nicht interessant. Das Ergebnis zählt.

Die Regel: Wenn der Leser nach dem Akteur fragen würde, schreib aktiv. Wenn niemand fragt, darf das Passiv bleiben.

---

## In der Praxis

**Vale-Regel** (experimentell):

```yaml
extends: existence
message: "Passiv erkannt: '%s'. Wer handelt hier?"
level: warning
tokens:
  - 'wird\s+\w+t\b'
  - 'wurde\s+\w+t\b'
  - 'werden\s+\w+t\b'
  - 'worden'
```

**LLM-Prompt:**

> Prüfe diesen Text auf Passivkonstruktionen. Zeige jede Stelle. Schlage eine aktive Umformulierung vor. Nenne den Akteur, der im Original fehlt.

---

## Verwandte Regeln

- **Verben statt Nominalisierungen** — Das Passiv und der Nominalstil sind Geschwister. Wo das eine auftaucht, ist das andere nicht weit.
- **Ein Gedanke, ein Satz** — Passivsätze sind oft lang, weil sie Umwege nehmen. Kürze den Satz, und das Passiv verschwindet von selbst.
