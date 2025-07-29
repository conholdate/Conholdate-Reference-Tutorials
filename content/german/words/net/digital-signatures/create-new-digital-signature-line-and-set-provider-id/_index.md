---
"description": "Erfahren Sie, wie Sie mit Aspose.Words für .NET programmgesteuert Signaturzeilen zu Ihren Word-Dokumenten hinzufügen. Diese umfassende Anleitung deckt alles ab, von der Einrichtung Ihrer Entwicklungsumgebung über das Einfügen von Signaturzeilen bis hin zum sicheren Signieren von Dokumenten."
"linktitle": "Neue digitale Signaturzeile erstellen und Anbieter-ID festlegen"
"second_title": "Aspose.Words Dokumentverarbeitungs-API"
"title": "Neue digitale Signaturzeile erstellen und Anbieter-ID festlegen"
"url": "/de/words/net/digital-signatures/create-new-digital-signature-line-and-set-provider-id/"
"weight": 10
---

## Einführung

Hallo Technikbegeisterte! Wollten Sie schon immer Signaturzeilen in Ihren Word-Dokumenten automatisieren? Heute zeigen wir Ihnen, wie Sie dies mit Aspose.Words für .NET erreichen. Diese Schritt-für-Schritt-Anleitung führt Sie durch die Erstellung einer Signaturzeile und die Festlegung der Anbieter-ID und gestaltet so Ihre Dokumentverarbeitung effizienter und schlanker.

## Voraussetzungen

Bevor wir loslegen, stellen wir sicher, dass Sie alles eingerichtet haben:

1. Aspose.Words für .NET: Falls noch nicht installiert, laden Sie es herunter [Hier](https://releases.aspose.com/words/net/).
2. Entwicklungsumgebung: Verwenden Sie Visual Studio oder ein beliebiges C#-Entwicklungs-Setup.
3. .NET Framework: Stellen Sie sicher, dass das .NET Framework auf Ihrem Computer installiert ist.
4. PFX-Zertifikat: Zum Signieren von Dokumenten benötigen Sie ein PFX-Zertifikat, das Sie von einer vertrauenswürdigen Zertifizierungsstelle erhalten.

## Importieren der erforderlichen Namespaces

Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Lassen Sie uns nun in die Details der Erstellung einer neuen Signaturzeile und der Festlegung der Anbieter-ID eintauchen.

## Schritt 1: Erstellen Sie ein neues Dokument

Zuerst müssen wir ein neues Word-Dokument erstellen, das als Vorlage für unsere Signaturzeile dient:

```csharp
// Geben Sie den Pfad zu Ihrem Dokumentverzeichnis an.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Hier initialisieren wir ein neues `Document` und ein `DocumentBuilder`, wodurch wir problemlos Elemente hinzufügen können.

## Schritt 2: Signaturzeilenoptionen definieren

Als Nächstes definieren wir die Optionen für unsere Signaturzeile, einschließlich Name, Titel, E-Mail-Adresse und anderer relevanter Details des Unterzeichners:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Diese Optionen helfen dabei, die Signaturzeile zu personalisieren und sie klar und professionell zu gestalten.

## Schritt 3: Einfügen der Signaturzeile

Nachdem wir unsere Optionen bereitgelegt haben, können wir nun die Signaturzeile in das Dokument einfügen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Der `InsertSignatureLine` Die Methode fügt die Signaturzeile hinzu und wir weisen ihr eine eindeutige Anbieter-ID zu.

## Schritt 4: Speichern Sie das Dokument

Nachdem wir die Signaturzeile eingefügt haben, speichern wir das Dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Dadurch wird Ihr Dokument mit der neu hinzugefügten Signaturzeile gespeichert.

## Schritt 5: Signaturoptionen einrichten

Jetzt konfigurieren wir die Signaturoptionen, einschließlich der Signaturzeilen-ID, der Anbieter-ID, der Kommentare und der Signaturzeit:

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Diese Einstellungen stellen sicher, dass das Dokument mit den richtigen Angaben signiert wird.

## Schritt 6: Zertifikatsinhaber erstellen

Um das Dokument zu signieren, müssen wir mithilfe des PFX-Zertifikats einen Zertifikatsinhaber erstellen:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ersetzen `"morzal.pfx"` mit Ihrem tatsächlichen Zertifikatsdateinamen und `"aw"` mit Ihrem Zertifikatspasswort.

## Schritt 7: Unterschreiben Sie das Dokument

Abschließend unterschreiben wir das Dokument mit dem Dienstprogramm für digitale Signaturen:

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Dieser Vorgang signiert das Dokument und speichert es als neue Datei.

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.Words für .NET erfolgreich eine Signaturzeile erstellt und die Anbieter-ID in einem Word-Dokument festgelegt. Diese leistungsstarke Bibliothek vereinfacht die Dokumentverarbeitung und optimiert Ihren Workflow. Probieren Sie es aus und überzeugen Sie sich selbst, wie es Ihre Projekte verbessern kann!

## Häufig gestellte Fragen

### Kann ich das Erscheinungsbild der Signaturzeile anpassen?
Auf jeden Fall! Sie können verschiedene Optionen im `SignatureLineOptions` passend zu Ihrem Stil und Ihren Anforderungen.

### Was ist, wenn ich kein PFX-Zertifikat habe?
Sie müssen eines von einer vertrauenswürdigen Zertifizierungsstelle beziehen, da es für die digitale Signatur von Dokumenten unerlässlich ist.

### Kann ich einem Dokument mehrere Signaturzeilen hinzufügen?
Ja, Sie können mehrere Signaturzeilen hinzufügen, indem Sie den Einfügevorgang mit verschiedenen Optionen wiederholen.

### Ist Aspose.Words für .NET mit .NET Core kompatibel?
Ja, Aspose.Words für .NET unterstützt .NET Core und ist daher vielseitig für verschiedene Entwicklungsumgebungen einsetzbar.

### Wie sicher sind die digitalen Signaturen?
Mit Aspose.Words erstellte digitale Signaturen sind äußerst sicher, sofern Sie ein gültiges und vertrauenswürdiges Zertifikat verwenden.