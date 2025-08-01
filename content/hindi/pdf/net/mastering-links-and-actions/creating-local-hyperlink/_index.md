---
"description": "जानें कि .NET के लिए Aspose.PDF का उपयोग करके स्थानीय हाइपरलिंक बनाकर अपने PDF दस्तावेज़ों में नेविगेशन कैसे बेहतर बनाया जाए। यह चरण-दर-चरण ट्यूटोरियल आपको पूरी प्रक्रिया से परिचित कराता है।"
"linktitle": "पीडीएफ फाइल में स्थानीय हाइपरलिंक बनाना"
"second_title": ".NET API संदर्भ के लिए Aspose.PDF"
"title": "पीडीएफ फाइल में स्थानीय हाइपरलिंक बनाना"
"url": "/hi/pdf/net/mastering-links-and-actions/creating-local-hyperlink/"
"weight": 40
---

## परिचय

इस गाइड में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में स्थानीय हाइपरलिंक बनाने की प्रक्रिया से परिचित कराएँगे। हम हर चरण को स्पष्ट रूप से समझाएँगे, ताकि भले ही आप PDF में नए हों, आप इसे आसानी से कर पाएँ।

## आवश्यक शर्तें

कोड में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. विजुअल स्टूडियो: इसे यहां से डाउनलोड करें [विजुअल स्टूडियो वेबसाइट](https://visualstudio.microsoft.com/).
2. .NET के लिए Aspose.PDF: लाइब्रेरी को डाउनलोड करें [Aspose वेबसाइट](https://releases.aspose.com/pdf/net/)यह लाइब्रेरी पीडीएफ हेरफेर के लिए सुविधाओं का एक समृद्ध सेट प्रदान करती है।
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग से परिचित होना सहायक होगा, लेकिन चिंता न करें; हम कोड को लाइन दर लाइन समझाएंगे।
4. .NET Framework: सुनिश्चित करें कि आपकी मशीन पर .NET Framework स्थापित है। Aspose.PDF पर आवश्यकताओं की जाँच करें। [प्रलेखन](https://reference.aspose.com/pdf/net/).

इन पूर्वापेक्षाओं के साथ, आप अपने PDF दस्तावेज़ों में स्थानीय हाइपरलिंक बनाना सीखने के लिए तैयार हैं!

## आवश्यक पैकेज आयात करना

अब जब आप पूरी तरह से तैयार हो गए हैं, तो अब समय आ गया है कि आप अपने C# प्रोजेक्ट में आवश्यक पैकेजों को आयात करें।

### अपना प्रोजेक्ट खोलें

अपना मौजूदा .NET प्रोजेक्ट खोलें या Visual Studio में एक नया प्रोजेक्ट बनाएँ। अगर आप नया प्रोजेक्ट शुरू कर रहे हैं, तो स्टार्टअप स्क्रीन से "नया प्रोजेक्ट बनाएँ" चुनें।

### Aspose.PDF में संदर्भ जोड़ें

सॉल्यूशन एक्सप्लोरर में अपने प्रोजेक्ट फ़ोल्डर में "Dependencies" पर राइट-क्लिक करें। "Manage NuGet Packages" चुनें, खोजें `Aspose.PDF`, और उपलब्ध नवीनतम संस्करण इंस्टॉल करें। इससे आपको PDF बनाने और उनमें बदलाव करने के लिए ज़रूरी सभी टूल मिल जाएँगे।

### नामस्थान आयात करें

अपनी .cs फ़ाइल के शीर्ष पर, निम्नलिखित using निर्देश जोड़ें:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

ये निर्देश आपको लाइब्रेरी की सुविधाओं तक निर्बाध पहुंच प्रदान करते हैं।

आइए स्थानीय हाइपरलिंक बनाने की प्रक्रिया को सरल चरणों में विभाजित करें।

## चरण 1: दस्तावेज़ इंस्टेंस सेट अप करें

का एक नया उदाहरण बनाएँ `Document` क्लास, उस पीडीएफ फाइल का प्रतिनिधित्व करता है जिसके साथ आप काम करेंगे।

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // अपनी दस्तावेज़ निर्देशिका सेट करें
Document doc = new Document(); // दस्तावेज़ उदाहरण बनाएँ
```

प्रतिस्थापित करें `"YOUR_DOCUMENT_DIRECTORY"` आपके सिस्टम पर वास्तविक पथ के साथ जहां पीडीएफ सहेजा जाएगा।

## चरण 2: दस्तावेज़ में एक पृष्ठ जोड़ें

इसके बाद, अपने पीडीएफ दस्तावेज़ में एक पृष्ठ जोड़ें।

```csharp
Page page = doc.Pages.Add(); // एक नया पृष्ठ जोड़ें
```

यह पंक्ति दस्तावेज़ में एक नया पृष्ठ जोड़ती है, जहां आपकी सारी सामग्री रखी जाएगी।

## चरण 3: एक टेक्स्ट फ़्रैगमेंट बनाएँ

अब, आइए एक ऐसा पाठ बनाएं जो क्लिक करने योग्य लिंक के रूप में कार्य करेगा।

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7"); // एक पाठ खंड बनाएँ
```

यह `TextFragment` वह पाठ प्रदर्शित करेगा जिस पर उपयोगकर्ता क्लिक कर सकते हैं।

## चरण 4: स्थानीय हाइपरलिंक बनाएँ

अब, एक स्थानीय हाइपरलिंक बनाएं जो पृष्ठ 7 की ओर इंगित करे।

```csharp
LocalHyperlink link = new LocalHyperlink(); // एक स्थानीय हाइपरलिंक बनाएँ
link.TargetPageNumber = 7; // लिंक के लिए लक्ष्य पृष्ठ सेट करें
text.Hyperlink = link; // पाठ खंड के लिए हाइपरलिंक सेट करें
```

The `LocalHyperlink` क्लास आपको हाइपरलिंक के लिए लक्ष्य पृष्ठ संख्या निर्दिष्ट करने की अनुमति देता है।

## चरण 5: पृष्ठ पर पाठ खंड जोड़ें

आपके द्वारा बनाए गए पृष्ठ पर क्लिक करने योग्य पाठ जोड़ें.

```csharp
page.Paragraphs.Add(text); // पृष्ठ पर पाठ अंश जोड़ें
```

यह पंक्ति आपके पाठ को पृष्ठ के अनुच्छेदों के संग्रह में जोड़ती है।

## चरण 6: एक और टेक्स्ट फ़्रैगमेंट बनाएँ (वैकल्पिक)

आइए पृष्ठ 1 पर वापस जाने के लिए एक और हाइपरलिंक जोड़ें।

```csharp
TextFragment textBack = new TextFragment("Link to page 1"); // एक नया पाठ खंड बनाएँ
textBack.IsInNewPage = true; // इंगित करें कि यह एक नए पृष्ठ पर होना चाहिए
```

## चरण 7: दूसरा स्थानीय हाइपरलिंक सेट करें

पृष्ठ 1 के लिए एक अन्य स्थानीय हाइपरलिंक बनाएं।

```csharp
Aspose.Pdf.LocalHyperlink linkBack = new Aspose.Pdf.LocalHyperlink(); // एक अन्य स्थानीय हाइपरलिंक बनाएँ
linkBack.TargetPageNumber = 1; // दूसरे हाइपरलिंक के लिए लक्ष्य पृष्ठ सेट करें
textBack.Hyperlink = linkBack; // दूसरे पाठ खंड के लिए हाइपरलिंक सेट करें
```

## चरण 8: नए पृष्ठ पर दूसरा पाठ खंड जोड़ें

दूसरे पाठ खंड को उसके पृष्ठ पर जोड़ें।

```csharp
Page newPage = doc.Pages.Add(); // दूसरे लिंक के लिए एक नया पृष्ठ जोड़ें
newPage.Paragraphs.Add(textBack); // नए पृष्ठ पर पाठ अंश जोड़ें
```

## चरण 9: दस्तावेज़ सहेजें

अंत में, अपना दस्तावेज़ सहेजें.

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // आउटपुट फ़ाइल नाम निर्दिष्ट करें
doc.Save(dataDir); // अद्यतन किए गए दस्तावेज़ को सहेजें
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```

यह पंक्ति आपके निर्देशिका पथ को फ़ाइल नाम के साथ जोड़ती है, और `Save()` विधि आपके दस्तावेज़ को सहेजती है.

## निष्कर्ष

.NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइलों में स्थानीय हाइपरलिंक बनाना एक व्यावहारिक सुविधा है जो नेविगेशन और उपयोगकर्ता अनुभव को बेहतर बनाती है। अब आपके पास अपने पाठकों को उनकी ज़रूरत की जानकारी तक सीधे पहुँचाने का ज्ञान है, जिससे आपकी PDF फ़ाइलें अधिक इंटरैक्टिव और उपयोगकर्ता-अनुकूल बन जाती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### .NET के लिए Aspose.PDF क्या है?
.NET के लिए Aspose.PDF एक लाइब्रेरी है जो डेवलपर्स को .NET फ्रेमवर्क का उपयोग करके प्रोग्रामेटिक रूप से PDF दस्तावेज़ बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है।

### क्या मैं बाहरी वेब पेजों के लिए हाइपरलिंक बना सकता हूँ?
हां, Aspose.PDF पीडीएफ के भीतर स्थानीय हाइपरलिंक के अलावा बाहरी यूआरएल के लिए हाइपरलिंक बनाने का भी समर्थन करता है।

### क्या Aspose.PDF के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
बिल्कुल! आप मुफ़्त ट्रायल का लाभ यहाँ से उठा सकते हैं [Aspose वेबसाइट](https://releases.aspose.com/).

### Aspose कौन सी प्रोग्रामिंग भाषाओं का समर्थन करता है?
एस्पोज विभिन्न प्रोग्रामिंग भाषाओं के लिए लाइब्रेरी प्रदान करता है, जिनमें जावा, सी++, और पायथन आदि शामिल हैं।

### मैं Aspose उत्पादों के लिए समर्थन कैसे प्राप्त करूं?
आप के माध्यम से सहायता प्राप्त कर सकते हैं [एस्पोज़ फ़ोरम](https://forum.aspose.com/c/pdf/10).