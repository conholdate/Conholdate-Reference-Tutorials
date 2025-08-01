---
"description": ".NET के लिए Aspose.CAD का उपयोग करके CAD लेआउट को विभिन्न रास्टर इमेज फ़ॉर्मेट में कुशलतापूर्वक परिवर्तित करना सीखें। यह विस्तृत मार्गदर्शिका आपको स्पष्ट कोड के साथ पूरी प्रक्रिया समझाती है।"
"linktitle": "CAD को रास्टर छवि रूपांतरण में निर्यात करें"
"second_title": "Aspose.CAD .NET - CAD और BIM फ़ाइल स्वरूप"
"title": ".NET के लिए Aspose.CAD के साथ CAD को रास्टर छवि रूपांतरण में निर्यात करें"
"url": "/hi/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## परिचय

क्या आप .NET के लिए Aspose.CAD का उपयोग करके CAD लेआउट को आसानी से रैस्टर इमेज फ़ॉर्मेट में बदलना चाहते हैं? यह चरण-दर-चरण मार्गदर्शिका आपको इस प्रक्रिया को समझने में मदद करने के लिए डिज़ाइन की गई है, जिसमें एक सहज अनुभव के लिए संक्षिप्त कोड स्निपेट भी शामिल हैं। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह ट्यूटोरियल सभी कौशल स्तरों के लिए बहुमूल्य जानकारी प्रदान करता है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.CAD for .NET लाइब्रेरी: लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें [Aspose.CAD वेबसाइट](https://releases.aspose.com/cad/net/).
- सीएडी ड्राइंग फ़ाइल: अपनी सीएडी ड्राइंग फ़ाइल (जैसे, `conic_pyramid.dxf`) रूपांतरण के लिए तैयार है।

## आवश्यक नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, आपको Aspose.CAD फ़ंक्शन का उपयोग करने के लिए आवश्यक नेमस्पेस इम्पोर्ट करने होंगे। अपने कोड के शीर्ष पर निम्नलिखित जोड़ें:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## चरण 1: अपना CAD ड्राइंग लोड करें

सबसे पहले, निर्देशिका निर्दिष्ट करें और अपनी CAD फ़ाइल को इमेज इंस्टैंस में लोड करें:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// CAD ड्राइंग लोड करें
using (var image = Image.Load(sourceFilePath))
{
    // अगले चरणों पर आगे बढ़ें
}
```

## चरण 2: रैस्टराइज़ेशन विकल्प बनाएँ

इसके बाद, आउटपुट छवि के लिए वांछित आयाम निर्धारित करते हुए, रास्टराइज़ेशन विकल्प सेट करें:

```csharp
// CadRasterizationOptions आरंभ करें
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## चरण 3: रूपांतरण के लिए परतें निर्दिष्ट करें

यदि आप विशिष्ट परतों को परिवर्तित करना चाहते हैं, तो उन्हें अपने रास्टराइज़ेशन विकल्पों में जोड़ें:

```csharp
// परिवर्तित करने के लिए परत निर्दिष्ट करें
rasterizationOptions.Layers = new [] { "LayerA" };
```

## चरण 4: JPEG निर्यात विकल्प सेट करें

अब, उस छवि प्रारूप के लिए विकल्प बनाएं जिसे आप निर्यात करना चाहते हैं (इस मामले में JPEG):

```csharp
// निर्यात के लिए JpegOptions बनाएँ
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## चरण 5: JPEG प्रारूप में निर्यात करें

अंत में, परिवर्तित छवि को सहेजें:

```csharp
// आउटपुट फ़ाइल पथ परिभाषित करें और छवि सहेजें
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## अतिरिक्त सुविधा: सभी परतों को परिवर्तित करें

अपने CAD ड्राइंग में सभी परतों को परिवर्तित करने के लिए, आप इस तरह की विधि लागू कर सकते हैं:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // परतों के माध्यम से पुनरावृति करें और प्रत्येक को एक अलग JPEG फ़ाइल के रूप में सहेजें
    // आपका कार्यान्वयन कोड यहां
}
```

## निष्कर्ष

बधाई हो! आपने Aspose.CAD for .NET का उपयोग करके CAD लेआउट को रैस्टर इमेज फ़ॉर्मेट में प्रभावी ढंग से परिवर्तित करना सीख लिया है। यह मार्गदर्शिका कुशल CAD रूपांतरणों के इच्छुक डेवलपर्स के लिए एक सरल दृष्टिकोण प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं विभिन्न छवि प्रारूपों में निर्यात कर सकता हूँ?

बिल्कुल! बस अदला-बदली करें `JpegOptions` अन्य प्रारूप विकल्पों के साथ, जैसे `PngOptions` या `BmpOptions`, आपकी आवश्यकताओं के आधार पर।

### क्या इसका परीक्षण संस्करण उपलब्ध है?

हां, आप इस लिंक का अनुसरण करके कार्यक्षमता का पता लगाने के लिए एक परीक्षण संस्करण डाउनलोड कर सकते हैं [जोड़ना](https://releases.aspose.com/cad/net/).

### मैं Aspose.CAD के लिए समर्थन कहां पा सकता हूं?

सामुदायिक सहायता के लिए, Aspose.CAD देखें [मंच](https://forum.aspose.com/c/cad/19), या अधिक समर्पित सहायता के लिए लाइसेंस खरीदने पर विचार करें।

### क्या अस्थायी लाइसेंस संभव है?

हाँ, अस्थायी लाइसेंस उपलब्ध हैं; आप इसके लिए अनुरोध कर सकते हैं [यहाँ](https://purchase.conholdate.com/temporary-license/).

### मैं विस्तृत दस्तावेज कहां से प्राप्त कर सकता हूं?

विस्तृत दस्तावेज़ देखें [यहाँ](https://reference.aspose.com/cad/net/) अधिक जानकारी के लिए.