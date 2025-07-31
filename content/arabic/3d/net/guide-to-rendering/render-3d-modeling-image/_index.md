---
"description": "تعلم كيفية إنشاء وتخصيص نماذج ثلاثية الأبعاد بدائية، بما في ذلك الصناديق والأسطوانات، وحفظها بتنسيق FBX بكل سهولة. سواء كنت مبتدئًا أو خبيرًا في تطوير البرمجيات، ستجد في هذا البرنامج التعليمي خطوة بخطوة ما يناسبك."
"linktitle": "عرض صورة نموذجية ثلاثية الأبعاد من الكاميرا"
"second_title": "واجهة برمجة تطبيقات Aspose.3D .NET"
"title": "عرض صورة نموذجية ثلاثية الأبعاد باستخدام Aspose.3D لـ .NET"
"url": "/ar/3d/net/guide-to-rendering/render-3d-modeling-image/"
"weight": 11
---

## مقدمة

يُعدّ تحويل النماذج ثلاثية الأبعاد إلى صور مذهلة مهارةً أساسيةً في تطوير البرمجيات، خاصةً عند استخدام مكتبات قوية مثل Aspose.3D لـ .NET. في هذه المقالة، سنرشدك خلال عملية تحويل صورة نموذج ثلاثي الأبعاد من منظور الكاميرا. في النهاية، ستكتسب المعرفة اللازمة لإنشاء صور ثلاثية الأبعاد عالية الدقة، وتعديل زوايا الكاميرا، واستخدام إضاءة متقدمة لتحسين جودة الصورة.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية لديك لتقديم صور ثلاثية الأبعاد بنجاح باستخدام Aspose.3D لـ .NET:

- مكتبة Aspose.3D لـ .NET: أولاً، نزّل مكتبة Aspose.3D لـ .NET. يمكنك تثبيتها باستخدام NuGet أو تنزيلها مباشرةً من [صفحة إصدارات Aspose](https://releases.aspose.com/3d/net/).
- نموذج ثلاثي الأبعاد: جهّز نموذجك ثلاثي الأبعاد بصيغة متوافقة، مثل OBJ أو FBX أو 3DS. في هذا البرنامج التعليمي، سنستخدم `Aspose3D.obj` ملف.
- بيئة تطوير .NET: تأكد من وجود بيئة تطوير .NET فعّالة. يفترض هذا البرنامج التعليمي أنك تستخدم Visual Studio أو بيئة تطوير متكاملة مشابهة.

## استيراد مساحات الأسماء الضرورية

الخطوة الأولى في إعداد مشروعك هي تضمين مساحات الأسماء اللازمة لـ Aspose.3D. سيسمح هذا لكودك بالوصول إلى وظيفة Aspose.3D التي ستساعدك في تحميل النموذج، وإعداد الكاميرا، والإضاءة، وعرض المشهد.

```csharp
using System;
using System.IO;
using System.Collections;
using Aspose.ThreeD;
using Aspose.ThreeD.Animation;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Formats;
using Aspose.ThreeD.Utilities;
using System.Drawing;
using System.Drawing.Imaging;
```

## الخطوة 1: تحميل المشهد ثلاثي الأبعاد

الخطوة الأولى في أي سير عمل لعرض ثلاثي الأبعاد هي تحميل المشهد، الذي يتكون من النموذج والكاميرا والإضاءة وأي عناصر أخرى مطلوبة لعرض الصورة. إليك كيفية تحميل نموذجك ثلاثي الأبعاد إلى المشهد:

```csharp
Scene scene = new Scene();
var path = "YourModelPath/Aspose3D.obj";  // حدد مسار النموذج الخاص بك هنا
scene.Open(path);
```

## الخطوة 2: إعداد الكاميرا

يُعدّ ضبط الكاميرا المناسبة أمرًا بالغ الأهمية لالتقاط المشهد من المنظور المطلوب. في هذه الخطوة، سننشئ كاميرا منظورية، ونضبط مستوياتها القريبة والبعيدة للعمق، ونضع الكاميرا داخل المشهد لالتقاط النموذج بشكل صحيح.

```csharp
Camera cam = new Camera(ProjectionType.Perspective);
cam.NearPlane = 1;
cam.FarPlane = 500;
scene.RootNode.CreateChildNode(cam).Transform.Translation = new Vector3(170, 16, 130);  // وضع الكاميرا
cam.LookAt = new Vector3(28, 0, -30);  // ضبط نقطة التركيز للكاميرا
```

## الخطوة 3: إضافة الإضاءة إلى المشهد

تلعب الإضاءة دورًا أساسيًا في تحسين مظهر النموذج ثلاثي الأبعاد. يتيح لك Aspose.3D إضافة أنواع مختلفة من الإضاءة، مثل الإضاءة النقطية، والإضاءة الاتجاهية، والإضاءة الكاشفة، لإضاءة المشهد. في هذه الخطوة، سنضيف مزيجًا من هذه الإضاءة لجعل النموذج يبدو أكثر واقعية.

```csharp
scene.RootNode.CreateChildNode(new Light()
{
    LightType = LightType.Point,
    ConstantAttenuation = 0.3,
    Color = new Vector3(Color.White)
}).Transform.Translation = new Vector3(30, 10, 10);

scene.RootNode.CreateChildNode(new Light()
{
    LightType = LightType.Directional,
    ConstantAttenuation = 0.3,
    Direction = new Vector3(-0.3, -0.4, 0.3),
    Color = new Vector3(Color.White)
});

scene.RootNode.CreateChildNode(new Light()
{
    LightType = LightType.Spot,
    CastShadows = true,
    LookAt = new Vector3(28, 10, -30),
    Color = new Vector3(Color.White)
}).Transform.Translation = new Vector3(40, 10, 50);
```

## الخطوة 4: تحديد خيارات عرض الصورة

بعد أن أصبح لدينا مشهدنا مع النموذج والكاميرا والإضاءة، حان وقت تحديد خيارات العرض. تتيح لك هذه الخيارات تخصيص لون الخلفية، وتفعيل الظلال، وتعيين دلائل الملمس للحصول على تأثير أكثر واقعية.

```csharp
ImageRenderOptions opt = new ImageRenderOptions();
opt.BackgroundColor = Color.AliceBlue;  // تعيين لون الخلفية
opt.AssetDirectories.Add("YourDocumentDirectory" + "textures");  // تعيين دليل الملمس
opt.EnableShadows = true;  // تمكين الظلال للعمق
```

## الخطوة 5: تقديم المشهد

بعد إعداد كل شيء، الخطوة الأخيرة هي تحويل النموذج ثلاثي الأبعاد إلى ملف صورة. يمكنك تحديد حجم الصورة وتنسيقها، وسيتولى Aspose.3D الباقي.

```csharp
scene.Render(cam, "YourOutputDirectory/Render3DModelImageFromCamera.png", new Size(1024, 1024), ImageFormat.Png, opt);
```

سيؤدي هذا إلى تقديم صورة النموذج ثلاثي الأبعاد إلى دليل الإخراج المحدد بتنسيق PNG.

## خاتمة

تهانينا! لقد تعلمت الآن كيفية عرض صورة نموذج ثلاثي الأبعاد من منظور الكاميرا باستخدام Aspose.3D لـ .NET. باتباع الخطوات السابقة، يمكنك تجربة نماذج مختلفة، ومواضع كاميرات، وإعدادات إضاءة مختلفة لإنشاء تصورات ثلاثية الأبعاد أكثر ديناميكية وجاذبية بصريًا. يوفر لك Aspose.3D المرونة لتخصيص عروضك ثلاثية الأبعاد لتناسب احتياجات مشروعك.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.3D لـ .NET مع أدوات النمذجة ثلاثية الأبعاد الأخرى؟

نعم، يدعم Aspose.3D تنسيقات نماذج ثلاثية الأبعاد المختلفة مثل OBJ وFBX و3DS، مما يجعله متوافقًا مع أدوات النمذجة الشائعة مثل Blender و3ds Max وMaya.

### كيف يمكنني إصلاح مشكلات العرض؟

لاستكشاف الأخطاء وإصلاحها، تحقق من [منتدى Aspose.3D](https://forum.aspose.com/c/3d/18) للحصول على حلول لمشاكل العرض الشائعة. يمكنك أيضًا الرجوع إلى الوثائق للحصول على إرشادات مفصلة.

### هل هناك نسخة تجريبية مجانية متاحة؟

نعم، تقدم Aspose [نسخة تجريبية مجانية](https://releases.aspose.com/) لتتمكن من استكشاف كافة ميزات Aspose.3D وتقييم قدراته قبل الشراء.

### أين يمكنني العثور على وثائق شاملة؟

يمكنك العثور على وثائق مفصلة لـ Aspose.3D لـ .NET على [صفحة التوثيق](https://reference.aspose.com/3d/net/)، والذي يوفر تغطية متعمقة لميزات المكتبة ووظائفها.

### كيف يمكنني شراء Aspose.3D لـ .NET؟

لشراء Aspose.3D لـ .NET، قم بزيارة [صفحة الشراء](https://purchase.conholdate.com/buy)، حيث يمكنك اختيار الترخيص الذي يناسب احتياجاتك.