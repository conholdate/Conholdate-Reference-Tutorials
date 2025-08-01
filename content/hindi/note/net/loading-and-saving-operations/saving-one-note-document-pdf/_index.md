---
"description": ".NET के लिए Aspose.Note का उपयोग करके Microsoft OneNote दस्तावेज़ों को PDF फ़ाइलों के रूप में कुशलतापूर्वक सहेजना सीखें। यह मार्गदर्शिका आपको आवश्यक पूर्वापेक्षाओं से परिचित कराती है और उपयोगी FAQ प्रदान करती है।"
"linktitle": "OneNote दस्तावेज़ों को PDF में सहेजना"
"second_title": "Aspose.Note .NET API"
"title": ".NET के लिए Aspose.Note का उपयोग करके OneNote दस्तावेज़ों को PDF में सहेजना"
"url": "/hi/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.Note का उपयोग करके दस्तावेज़ों को PDF फ़ॉर्मेट में कैसे सेव किया जाए। Aspose.Note एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft OneNote फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने में सक्षम बनाती है। हम पूर्वापेक्षाएँ, इम्पोर्ट नेमस्पेस, और विभिन्न पेज लेआउट में दस्तावेज़ों को PDF में सेव करने के लिए चरण-दर-चरण मार्गदर्शिकाएँ प्रदान करेंगे।

## आवश्यक शर्तें
1. विजुअल स्टूडियो: सुनिश्चित करें कि यह स्थापित है।
2. .NET के लिए Aspose.Note: लाइब्रेरी डाउनलोड करें और इंस्टॉल करें।
3. C# ज्ञान: भाषा की बुनियादी समझ आवश्यक है।

## आवश्यक नामस्थान आयात करना
आगे बढ़ने से पहले, अपने कोड में निम्नलिखित नामस्थान आयात करें:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## चरण 1: पत्र पृष्ठ सेटिंग्स के साथ पीडीएफ में सहेजें
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // इस पथ को अपडेट करें
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
OneNote दस्तावेज़ को लोड करता है और उसे अक्षर-आकार पृष्ठ सेटिंग्स का उपयोग करके PDF के रूप में सहेजता है।

## चरण 2: A4 पृष्ठ सेटिंग्स के साथ PDF में सहेजें (कोई ऊँचाई सीमा नहीं)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // इस पथ को अपडेट करें
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
चरण 1 के समान, लेकिन ऊंचाई सीमाओं के बिना A4 पृष्ठ सेटिंग्स का उपयोग करता है।

## निष्कर्ष
यह ट्यूटोरियल Aspose.Note का उपयोग करके OneNote फ़ाइलों को PDF फ़ॉर्मेट में बदलने का तरीका सफलतापूर्वक प्रदर्शित करता है। विभिन्न पृष्ठ सेटिंग्स का उपयोग करके, डेवलपर्स दस्तावेज़ प्रबंधन में लचीलापन प्राप्त करते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Note जटिल OneNote फ़ाइलों को संभाल सकता है?
हां, यह जटिल OneNote फ़ाइलों की विभिन्न विशेषताओं को प्रभावी ढंग से संभालता है।

### क्या Aspose.Note व्यावसायिक परियोजनाओं के लिए उपयुक्त है?
हां, लाइसेंस खरीदने के बाद आप इसका उपयोग व्यावसायिक अनुप्रयोगों के लिए कर सकते हैं।

### क्या Aspose.Note निःशुल्क परीक्षण प्रदान करता है?
हां, अन्वेषण के लिए निःशुल्क परीक्षण उपलब्ध है।

### मैं Aspose.Note के लिए दस्तावेज़ कहां पा सकता हूं?
विस्तृत दस्तावेज Aspose संदर्भ साइट पर उपलब्ध है।

### क्या आपको और सहायता की आवश्यकता है?
प्रश्नों और सहायता के लिए, Aspose.Note फ़ोरम देखें।