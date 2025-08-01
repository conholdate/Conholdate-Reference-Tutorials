---
"description": ".NET के लिए Aspose.Tasks में क्लास का लाभ उठाकर कई शर्तों के आधार पर प्रोजेक्ट कार्यों को फ़िल्टर करना सीखें। सारांश कार्यों और गैर-शून्य विशेषताओं जैसे मानदंडों को मिलाकर।"
"linktitle": "Aspose.Tasks में कार्य फ़िल्टरिंग और संचालन"
"second_title": "Aspose.Tasks .NET एपीआई"
"title": "Aspose.Tasks में कार्य फ़िल्टरिंग और संचालन"
"url": "/hi/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks में प्रोजेक्ट कार्यों की उन्नत फ़िल्टरिंग कैसे करें `Util.And` वर्ग। यह शक्तिशाली सुविधा डेवलपर्स को कई मानदंडों के आधार पर कार्यों को कुशलतापूर्वक फ़िल्टर करने की अनुमति देती है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. C# प्रोग्रामिंग का बुनियादी ज्ञान.
2. .NET के लिए Aspose.Tasks इंस्टॉल करें। अगर आपने अभी तक ऐसा नहीं किया है, तो आप इसे यहाँ से डाउनलोड कर सकते हैं [इस लिंक](https://releases.aspose.com/tasks/net/).
3. कोड लिखने और चलाने के लिए विजुअल स्टूडियो जैसा एक एकीकृत विकास वातावरण (आईडीई)।

## नामस्थान आयात करना

आरंभ करने के लिए, आपको अपने C# प्रोजेक्ट में आवश्यक नेमस्पेस आयात करने होंगे। इससे आप Aspose.Tasks द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँच सकेंगे।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## चरण 1: परियोजना आरंभ करें और कार्य एकत्रित करें

सबसे पहले, एक Aspose.Tasks प्रोजेक्ट को इनिशियलाइज़ करें और उसमें सभी टास्क इकट्ठा करें। प्रदर्शन के लिए, हम मान लेंगे कि एक प्रोजेक्ट फ़ाइल है जिसका नाम है `Project2.mpp`.

```csharp
// दस्तावेज़ निर्देशिका का पथ
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// सभी चाइल्ड टास्क एकत्रित करें
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## चरण 2: फ़िल्टर शर्तें परिभाषित करें

इस चरण में, हम कार्यों को फ़िल्टर करने के लिए शर्तें निर्धारित करेंगे। हमारे उदाहरण में, हम दो शर्तें बनाएंगे: एक सारांश कार्यों को फ़िल्टर करने के लिए और दूसरी यह सुनिश्चित करने के लिए कि कार्य शून्य न हों।

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## चरण 3: AND ऑपरेशन के साथ शर्तों को संयोजित करें

अगला कदम इन शर्तों को संयोजित करना है `Util.And` यह हमें एक संयुक्त शर्त बनाने की अनुमति देता है जो दोनों मानदंडों को अनिवार्य बनाती है।

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## चरण 4: संयुक्त शर्त और फ़िल्टर कार्य लागू करें

अब, आइए एकत्रित कार्यों पर संयुक्त शर्त लागू करें ताकि उन विशिष्ट कार्यों को फ़िल्टर किया जा सके जो दोनों शर्तों को पूरा करते हैं।

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## चरण 5: फ़िल्टर किए गए कार्यों का आउटपुट

अंत में, हम अपने फ़िल्टर किए गए कार्यों की पुनरावृत्ति करेंगे और प्रासंगिक विवरण प्रस्तुत करेंगे। इससे हमें उन कार्यों को समझने में मदद मिलेगी जो हमारे मानदंडों पर खरे उतरते हैं।

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने दिखाया कि .NET के लिए Aspose.Tasks में उन्नत फ़िल्टरिंग ऑपरेशन कैसे करें `Util.And` वर्ग। कई शर्तों को मिलाकर, हम कार्यों को प्रभावी ढंग से फ़िल्टर कर सकते हैं, जिससे हमारे परियोजना प्रबंधन अनुप्रयोगों की उपयोगिता बढ़ जाती है।

## अक्सर पूछे जाने वाले प्रश्न

### .NET के लिए Aspose.Tasks क्या है?

.NET के लिए Aspose.Tasks एक व्यापक API है जिसे डेवलपर्स के लिए .NET अनुप्रयोगों के भीतर प्रोग्रामेटिक रूप से Microsoft प्रोजेक्ट फ़ाइलों में हेरफेर करने के लिए डिज़ाइन किया गया है।

### क्या मैं Util.And का उपयोग करके दो से अधिक शर्तों को संयोजित कर सकता हूँ?

हां `Util.And` क्लास आपको कई स्थितियों को संयोजित करने की अनुमति देता है, जिससे आपकी आवश्यकताओं के अनुरूप जटिल फ़िल्टरिंग तर्क सक्षम होता है।

### क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण संस्करण उपलब्ध है?

हाँ, आप यहाँ से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं [इस लिंक](https://releases.aspose.com/).

### मैं Aspose.Tasks के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?

विस्तृत दस्तावेज़ उपलब्ध हैं [यहाँ](https://reference.aspose.com/tasks/net/).

### मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?

सहायता Aspose.Tasks सामुदायिक मंच के माध्यम से उपलब्ध है, जिसे एक्सेस किया जा सकता है [यहाँ](https://forum.aspose.com/c/tasks/15).