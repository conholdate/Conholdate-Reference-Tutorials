---
"description": "Erfahren Sie, wie Sie mit Aspose.Words für .NET nahtlos eine digitale Signatur zu Ihren Word-Dokumenten hinzufügen. Dieses umfassende Tutorial behandelt alles von der Einrichtung Ihrer Umgebung und dem Einfügen einer Signaturzeile bis hin zum Speichern und Überprüfen Ihrer signierten Dokumente."
"linktitle": "Neue Signaturzeile erstellen und unterschreiben"
"second_title": "Aspose.Words Dokumentverarbeitungs-API"
"title": "Neue Signaturzeile erstellen und unterschreiben"
"url": "/de/words/net/digital-signatures/create-and-sign-new-signature-line/"
"weight": 10
---

## Einführung

Möchten Sie einem Word-Dokument eine digitale Signatur hinzufügen? Mit Aspose.Words für .NET ist es einfacher als Sie denken! Dieses Tutorial führt Sie durch die Schritte zum Einrichten Ihrer Umgebung, zum Hinzufügen einer Signaturzeile und zum digitalen Signieren Ihres Dokuments. Los geht's!

## Voraussetzungen

Bevor Sie sich in den Code vertiefen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET - [Laden Sie es hier herunter](https://releases.aspose.com/words/net/).
2. .NET-Entwicklungsumgebung – Visual Studio ist ideal für diese Aufgabe.
3. Zu unterzeichnendes Dokument – Sie können ein neues Word-Dokument erstellen oder ein vorhandenes verwenden.
4. Zertifikatsdatei - A `.pfx` Datei ist für digitale Signaturen erforderlich.
5. Bild der Signaturzeile (optional) – Sie können eine Bilddatei für die Signatur einfügen.

## Erforderliche Namespaces importieren

Um die Funktionen von Aspose.Words zu nutzen, müssen Sie die folgenden Namespaces importieren:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Definieren Sie zunächst den Pfad zu Ihrem Dokumentverzeichnis. Hier speichern und rufen Sie Ihre Dokumente ab.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Geben Sie den Pfad Ihres Dokumentverzeichnisses an
```

## Schritt 2: Erstellen eines neuen Dokuments

Als Nächstes erstellen wir ein neues Word-Dokument. Dieses Dokument dient als Vorlage für Ihre Signaturzeile.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen der Signaturzeile

Verwenden Sie nun die `DocumentBuilder` Klasse zum Einfügen einer Signaturzeile in Ihr Dokument:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Schritt 4: Speichern des Dokuments

Nachdem Sie die Signaturzeile eingefügt haben, speichern Sie das Dokument. Dies ist ein entscheidender Schritt vor der Unterzeichnung.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Schritt 5: Konfigurieren der Signaturoptionen

Richten Sie die Optionen für den Signaturvorgang ein. Dazu gehört die Angabe der Signaturzeilen-ID und des optionalen Bildes, das mit der Signatur angezeigt werden soll.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf") // Pfad zu Ihrem Bild
};
```

## Schritt 6: Laden des Zertifikats

Laden Sie die zum Signieren des Dokuments erforderliche Zertifikatsdatei:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "your_certificate.pfx", "your_password"); // Dateinamen und Passwort anpassen
```

## Schritt 7: Unterzeichnen des Dokuments

Unterschreiben Sie das Dokument abschließend mit dem `DigitalSignatureUtil` Klasse. Speichern Sie das signierte Dokument unter einem neuen Namen zur späteren Verwendung.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.SignedDocument.docx", certHolder, signOptions);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich ein Word-Dokument erstellt, eine Signaturzeile hinzugefügt und es mit Aspose.Words für .NET digital signiert. Dieses leistungsstarke Tool vereinfacht die Dokumentenautomatisierung und stellt sicher, dass Ihre Verträge und formellen Dokumente sicher signiert und authentifiziert sind.

## Häufig gestellte Fragen

### Kann ich für die Signaturzeile andere Bildformate verwenden?

Ja, Sie können verschiedene Bildformate verwenden, darunter PNG, JPG und BMP.

### Ist es notwendig, eine `.pfx` Datei für das Zertifikat?

Ja, ein `.pfx` Datei ist ein Standardformat zum Speichern von Zertifikaten und privaten Schlüsseln für digitale Signaturen.

### Kann ich in einem einzigen Dokument mehrere Signaturzeilen hinzufügen?

Auf jeden Fall! Sie können mehrere Signaturzeilen einfügen, indem Sie den Einfügeschritt nach Bedarf wiederholen.

### Was ist, wenn ich kein digitales Zertifikat habe?

Sie müssen ein digitales Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle beziehen oder mithilfe von Tools wie OpenSSL eines generieren.

### Wie überprüfe ich die digitale Signatur im Dokument?

Sie können die digitale Signatur überprüfen, indem Sie das signierte Dokument in Word öffnen und die Signaturdetails prüfen, um seine Authentizität und Integrität zu bestätigen.