---
"description": "Tanuld meg, hogyan kezelheted a találkozókon résztvevők állapotát C# és Aspose.Email for .NET használatával. Lépésről lépésre útmutató forráskóddal."
"linktitle": "Résztvevői állapot beállítása találkozó résztvevőinek C#-vel"
"second_title": "Aspose.Email .NET e-mail feldolgozó API"
"title": "Résztvevői állapot beállítása találkozó résztvevőinek C#-vel"
"url": "/hu/email/net/handling-email-events-and-calendar/setting-participant-status-for-appointment-attendees/"
"weight": 16
---

## Bevezetés

Az Aspose.Email for .NET egy robusztus és funkciókban gazdag könyvtár, amelyet a .NET alkalmazásokban az e-mail-kezelés egyszerűsítésére terveztek. Ez az útmutató lépésről lépésre bemutatja a találkozók létrehozását és kezelését, a résztvevők hozzáadását és a résztvevők állapotának beállítását, biztosítva a hatékony integrációt a .NET projektekbe.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:

- A Visual Studio vagy egy kompatibilis C# IDE működő telepítése.
- Az Aspose.Email for .NET könyvtár legújabb verziója.
- C# és objektumorientált programozási alapismeretek.

A könyvtár telepítéséhez lásd a [letöltési oldal](https://releases.aspose.com/).

## Szükséges névterek importálása

Első lépésként adja meg a szükséges névtereket az időpontok és az e-mail-összetevők kezelésére szolgáló funkciók eléréséhez.

```csharp
using Aspose.Email;
using Aspose.Email.Calendar;
```

## Találkozópéldány létrehozása

Az Aspose.Emailben az időpontok ütemezett eseményeket, például megbeszéléseket vagy feladatokat jelölnek. Így hozhatsz létre egyet:

```csharp
var appointment = new Appointment(
    "Conference Room 101", 
    DateTime.Now, 
    DateTime.Now.AddHours(1), 
    new MailAddress("organizer@example.com"),
    new MailAddressCollection { "attendee1@example.com", "attendee2@example.com" }
);
```

- Helyszín: Meghatározza, hogy hol fog megtörténni a találkozó.
- Kezdőidő és Befejezőidő: Adja meg a találkozó időtartamát.
- Szervező és résztvevők: Határozza meg a résztvevőket és szerepköreiket.

## Résztvevők hozzáadása találkozókhoz

Az Aspose.Email lehetővé teszi a résztvevők programozott kezelését e-mail címükkel és részvételi állapotukkal.

```csharp
appointment.Attendees.Add(new MailAddress("john@example.com", "John Doe"));
appointment.Attendees.Add(new MailAddress("jane@example.com", "Jane Smith"));
```

## Résztvevői státuszok kezelése

A `ParticipantStatus` tulajdonság segít meghatározni, hogy egy résztvevő elfogadta, elutasította vagy feltételesen elfogadta-e a találkozóra szóló meghívást. Használja a következő felsorolási értékeket:

- Elfogadott
- Elutasítva
- Kísérleti

Példa:

```csharp
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Találkozók küldése értekezletmeghívóként

Miután a találkozó előkészítésre került, elküldheti meghívó e-mailben:

```csharp
var msg = new MailMessage();
msg.From = "organizer@example.com";
msg.To = new MailAddressCollection { "john@example.com", "jane@example.com" };
msg.Subject = "Team Meeting";
msg.AlternateViews.Add(appointment.RequestApointment());

var client = new SmtpClient("smtp.example.com", 587, "username", "password");
client.Send(msg);
```

## Következtetés

Az Aspose.Email for .NET leegyszerűsíti az időpont-kezelést a .NET alkalmazásokban, eszközöket biztosítva az ütemezett események hatékony létrehozásához, testreszabásához és kezeléséhez. Intuitív API-jával korszerűsítheti a kommunikációs munkafolyamatokat és biztosíthatja a zökkenőmentes integrációt.

## GYIK

### Mi az Aspose.Email .NET-hez?

Az Aspose.Email for .NET egy átfogó függvénykönyvtár e-mailek, találkozók és egyéb kapcsolódó funkciók kezelésére .NET alkalmazásokban.

### Testreszabhatom az időpont tulajdonságait?

Igen, az olyan tulajdonságok, mint a helyszín, a kezdési időpont és a résztvevők, teljes mértékben testreszabhatók.

### Támogatja a könyvtár az ismétlődő időpontfoglalásokat?

Igen, az Aspose.Email for .NET támogatja az ismétlődő találkozókat az ismétlődési minta API-ján keresztül.

### Hol kaphatok támogatást az Aspose.Email for .NET-hez?

Részletes dokumentációt és közösségi támogatást a következő címen érhet el: [támogatási oldal](https://forum.aspose.com/c/email/11).