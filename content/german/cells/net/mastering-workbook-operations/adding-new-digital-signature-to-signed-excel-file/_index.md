---
"description": "Erfahren Sie, wie Sie mit Aspose.Cells für .NET einer vorhandenen signierten Excel-Datei eine neue digitale Signatur hinzufügen. Diese umfassende Anleitung enthält alle Voraussetzungen, Schritt-für-Schritt-Anleitungen und Codebeispiele."
"linktitle": "Hinzufügen einer neuen digitalen Signatur zu einer signierten Excel-Datei"
"second_title": "Aspose.Cells .NET Excel-Verarbeitungs-API"
"title": "Hinzufügen einer neuen digitalen Signatur zu einer signierten Excel-Datei"
"url": "/de/cells/net/mastering-workbook-operations/adding-new-digital-signature-to-signed-excel-file/"
"weight": 12
---

## Einführung

In der heutigen digitalen Landschaft ist die Gewährleistung der Authentizität und Integrität von Dokumenten wichtiger denn je. Digitale Signaturen bieten eine zuverlässige Möglichkeit, die Unveränderlichkeit eines Dokuments und seine Herkunft aus einer legitimen Quelle zu überprüfen. Wenn Sie mit Excel-Dateien in .NET arbeiten und einer bereits signierten Datei eine neue digitale Signatur hinzufügen müssen, ist diese Anleitung genau das Richtige für Sie! Wir führen Sie durch den Prozess des Hinzufügens einer digitalen Signatur zu einer bereits signierten Excel-Datei mit Aspose.Cells für .NET.

## Voraussetzungen

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Cells für .NET: Laden Sie Aspose.Cells herunter und installieren Sie es von der [Release-Seite](https://releases.aspose.com/cells/net/).
2. .NET Framework: Stellen Sie sicher, dass auf Ihrem Computer das .NET Framework installiert ist und Sie mit den grundlegenden Konzepten der .NET-Programmierung vertraut sind.
3. Digitales Zertifikat: Erhalten Sie ein gültiges digitales Zertifikat im PFX-Format. Zum Testen können Sie ein selbstsigniertes Zertifikat erstellen.
4. Entwicklungsumgebung: Verwenden Sie eine IDE wie Visual Studio, um Ihren C#-Code zu schreiben und auszuführen.
5. Beispiel einer Excel-Datei: Sie verfügen über eine vorhandene, bereits digital signierte Excel-Datei, die als Ziel für das Hinzufügen einer neuen Signatur dient.

Nachdem diese Voraussetzungen erfüllt sind, können wir mit dem Code beginnen!

## Importieren Sie die erforderlichen Pakete

Fügen Sie oben in Ihrer C#-Datei die folgenden Namespaces ein, um auf die erforderlichen Klassen und Methoden zuzugreifen:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Schritt 1: Definieren Sie Ihre Verzeichnisse

Geben Sie die Verzeichnisse für Ihre Quelldateien und den Speicherort der Ausgabedatei an:

```csharp
// Quellverzeichnis
string sourceDir = "Your Document Directory"; // Ersetzen Sie es durch Ihr aktuelles Verzeichnis
// Ausgabeverzeichnis
string outputDir = "Your Document Directory"; // Ersetzen Sie es durch Ihr aktuelles Verzeichnis
```

## Schritt 2: Laden Sie die vorhandene signierte Arbeitsmappe

Laden Sie die bereits signierte Excel-Arbeitsmappe:

```csharp
// Laden Sie die Arbeitsmappe, die bereits digital signiert ist
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(sourceDir + "sampleDigitallySignedByCells.xlsx");
```

## Schritt 3: Erstellen Sie eine digitale Signatursammlung

Erstellen Sie eine Sammlung zur Verwaltung Ihrer digitalen Signaturen:

```csharp
// Erstellen Sie die digitale Signatursammlung
Aspose.Cells.DigitalSignatures.DigitalSignatureCollection dsCollection = new Aspose.Cells.DigitalSignatures.DigitalSignatureCollection();
```

## Schritt 4: Laden Sie Ihr Zertifikat

Laden Sie Ihr digitales Zertifikat, das zum Erstellen der neuen Signatur verwendet wird:

```csharp
// Zertifikatsdatei und ihr Passwort
string certFileName = sourceDir + "AsposeDemo.pfx"; // Ihre Zertifikatsdatei
string password = "aspose"; // Ihr Zertifikatspasswort

// Neues Zertifikat erstellen
System.Security.Cryptography.X509Certificates.X509Certificate2 certificate = new System.Security.Cryptography.X509Certificates.X509Certificate2(certFileName, password);
```

## Schritt 5: Erstellen Sie eine neue digitale Signatur

Erstellen Sie jetzt eine neue digitale Signatur und fügen Sie sie Ihrer Sammlung hinzu:

```csharp
// Neue digitale Signatur erstellen und zur Sammlung hinzufügen
Aspose.Cells.DigitalSignatures.DigitalSignature signature = new Aspose.Cells.DigitalSignatures.DigitalSignature(certificate, "Aspose.Cells added new digital signature in existing digitally signed workbook.", DateTime.Now);
dsCollection.Add(signature);
```

## Schritt 6: Hinzufügen der Signatursammlung zur Arbeitsmappe

Fügen Sie der Arbeitsmappe die Sammlung digitaler Signaturen hinzu:

```csharp
// Fügen Sie der Arbeitsmappe eine Sammlung digitaler Signaturen hinzu
workbook.AddDigitalSignature(dsCollection);
```

## Schritt 7: Speichern Sie die Arbeitsmappe

Speichern Sie die Arbeitsmappe mit der neuen digitalen Signatur:

```csharp
// Speichern der Arbeitsmappe
workbook.Save(outputDir + "outputDigitallySignedByCells.xlsx");
workbook.Dispose();
```

## Schritt 8: Erfolg bestätigen

Geben Sie bei erfolgreicher Ausführung Feedback:

```csharp
Console.WriteLine("Successfully added a digital signature to the existing signed Excel file.");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben einer bereits signierten Excel-Datei mit Aspose.Cells für .NET erfolgreich eine neue digitale Signatur hinzugefügt. Dieser Vorgang erhöht die Sicherheit Ihrer Dokumente und gewährleistet deren Authentizität und Integrität.

## Häufig gestellte Fragen

### Was ist eine digitale Signatur?

Eine digitale Signatur ist ein mathematisches Verfahren, das die Authentizität und Integrität digitaler Nachrichten oder Dokumente überprüft, sicherstellt, dass sie nicht verändert wurden, und die Identität des Unterzeichners bestätigt.

### Benötige ich zum Erstellen einer digitalen Signatur ein spezielles Zertifikat?

Ja, zum Erstellen einer gültigen digitalen Signatur ist ein digitales Zertifikat erforderlich, das von einer vertrauenswürdigen Zertifizierungsstelle (CA) ausgestellt wurde.

### Kann ich zum Testen ein selbstsigniertes Zertifikat verwenden?

Auf jeden Fall! Sie können ein selbstsigniertes Zertifikat für Entwicklungs- und Testzwecke verwenden. Für die Produktion empfiehlt sich jedoch die Verwendung eines Zertifikats einer vertrauenswürdigen Zertifizierungsstelle.

### Was passiert, wenn ich versuche, einem nicht signierten Dokument eine Signatur hinzuzufügen?

Wenn Sie versuchen, einem noch nicht signierten Dokument eine digitale Signatur hinzuzufügen, funktioniert dies problemlos, die Originalsignatur ist jedoch nicht vorhanden.

### Wo finde ich weitere Informationen zu Aspose.Cells?

Ausführliche Anleitungen und API-Referenzen finden Sie im [Aspose.Cells-Dokumentation](https://reference.aspose.com/cells/net/).