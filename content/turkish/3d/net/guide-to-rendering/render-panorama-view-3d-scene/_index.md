---
"description": "Aspose.3D kullanarak .NET uygulamalarınızda 3B sahnenin çarpıcı panoramik görüntüsünü nasıl oluşturacağınızı öğrenin. Sürükleyici sahne oluşturma için adım adım kılavuzumuzu izleyin."
"linktitle": "3B Sahnenin Panorama Görünümünü Oluşturun"
"second_title": "Aspose.3D .NET API"
"title": "Aspose.3D for .NET Kullanarak 3B Sahnenin Panorama Görünümünü Oluşturma"
"url": "/tr/3d/net/guide-to-rendering/render-panorama-view-3d-scene/"
"weight": 13
---

## giriiş

Sürükleyici ve panoramik 3B sahneler oluşturmak, uygulamalarını göz alıcı görsel efektlerle bir üst seviyeye taşımak isteyen geliştiriciler için ezber bozan bir çözümdür. İster bir oyun motoru, ister mimari görselleştirme veya sürükleyici web deneyimleri üzerinde çalışıyor olun, 3B sahneleri panorama olarak görüntülemek, kullanıcıların her açıdan dinamik bir görünüm deneyimi yaşamasını sağlar. Aspose.3D for .NET, bu özelliği .NET projelerinize sorunsuz bir şekilde entegre etmek için mükemmel bir araçtır. Bu kapsamlı kılavuz, Aspose.3D for .NET kullanarak bir 3B sahneden panorama oluşturma sürecinde size yol gösterecektir.

## Ön koşullar

İşleme sürecine başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:

- .NET için Aspose.3D: Başlamak için, 3B varlıkları ve işlemeyi yönetmek için gerekli tüm araçları sağlayan Aspose.3D'yi yüklemeniz gerekir. [.NET için Aspose.3D'yi indirin](https://releases.aspose.com/3d/net/) Başlamak için.
- .NET Geliştirme Ortamı: Tamamen yapılandırılmış bir .NET geliştirme ortamı gereklidir. Visual Studio veya uyumlu başka bir IDE'ye sahip olduğunuzdan emin olun.
- Örnek 3D Sahne Dosyası: Aşağıdaki formatlarda herhangi bir 3D sahneyi kullanabilirsiniz: `.glb`, `.fbx`, veya `.obj`Bu eğitimde basit bir "VirtualCity.glb" dosyası kullanacağız.

Bu ön koşulları yerine getirdikten sonra sahneyi kurmaya geçebiliriz.

## Gerekli Ad Alanlarını İçe Aktar

Aspose.3D ile çalışmak için projemize birkaç ad alanı aktarmamız gerekecek. Bu ad alanları, 3B nesneleri, kamera ayarlarını ve işleme seçeneklerini verimli bir şekilde düzenlemenizi sağlar.

```csharp
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Render;
using Aspose.ThreeD.Utilities;
using System;
using System.Drawing;
using System.Drawing.Imaging;
```

Bu ad alanları, 3B sahneyi yüklemek, kamerayı, aydınlatmayı yapılandırmak ve panoramik görünümü oluşturan render dokularını ayarlamak için gereklidir.

## Adım 1: 3B Sahneyi Uygulamanıza Yükleyin

İlk adım, 3B sahneyi uygulamanıza yüklemektir. Bu, şu şekilde gerçekleştirilebilir: `Scene` Aspose.3D tarafından sağlanan sınıf. Değiştir `"VirtualCity.glb"` 3D sahne dosyanızın yolunu belirtin.

```csharp
Scene scene = new Scene("path_to_your_scene/VirtualCity.glb");
```

The `Scene` nesne 3B sahneyi belleğe yükler, böylece onunla etkileşime girebilir ve işleme teknikleri uygulayabilirsiniz.

## Adım 2: Kamerayı ve Işıkları Ayarlayın

3B sahnenizin doğru şekilde çekildiğinden emin olmak için bir kamera ve uygun aydınlatma ayarlamanız gerekir. Kamera, sahnenin perspektifini kontrol etmenizi sağlarken, ışıklar nesneleri aydınlatmaya yardımcı olur.

```csharp
Camera cam = new Camera(ProjectionType.Perspective)
{
    NearPlane = 0.1,
    FarPlane = 200,
    RotationMode = RotationMode.FixedDirection
};

scene.RootNode.CreateChildNode(cam).Transform.Translation = new Vector3(5, 6, 0);

scene.RootNode.CreateChildNode(new Light() 
{ 
    LightType = LightType.Point 
}).Transform.Translation = new Vector3(-10, 7, -10);

scene.RootNode.CreateChildNode(new Light() 
{ 
    Color = new Vector3(Color.CadetBlue) 
}).Transform.Translation = new Vector3(49, 0, 49);
```

- Kamera Kurulumu: Kameranın yakın ve uzak düzlemleri, 3B sahnede görünür aralığı tanımlayacak şekilde ayarlanır.
- Işık Kurulumu: Sahneye derinlik ve gerçekçilik katmak için bir nokta ışığı ve belirli bir renkte bir ışık olmak üzere iki ışık eklenir.

## Adım 3: Renderer'ı Ayarlayın ve Render Hedeflerini Tanımlayın

Sahneniz, kameranız ve ışıklarınız ayarlandığına göre, bir sonraki adım işleyiciyi oluşturmak ve işleme hedeflerini tanımlamaktır. İşleyici, 3B görüntüleri oluşturmaktan sorumludur ve işleme hedefleri, nihai çıktının nereye kaydedileceğini belirler.

```csharp
using (var renderer = Renderer.CreateRenderer())
{
    IRenderTexture rt = renderer.RenderFactory.CreateCubeRenderTexture(new RenderParameters(false), 512, 512);
    IRenderTexture final = renderer.RenderFactory.CreateRenderTexture(new RenderParameters(false, 32, 0, 0), 1024 * 3, 1024);
}
```

- Küp İşleme Dokusu: Bu, panoramik görünüm için bir küp haritası işlemek için kullanılır. Burada 512x512 boyutlarında bir doku tanımlıyoruz.
- Son Render Dokusu: Bu, son dikdörtgen panoramik görünümü tutacak dokudur.

## Adım 4: Görünüm Penceresini Yapılandırın ve Sahneyi İşleyin

Render dokularını oluşturduktan sonra, kameranın 3B sahnede yakalayacağı bölgeyi tanımlayan görünüm alanını yapılandırmamız gerekiyor.

```csharp
rt.CreateViewport(cam, RelativeRectangle.FromScale(0, 0, 1, 1));
renderer.Render(rt);
```

Bu kod, küp haritası için görünüm alanını ayarlar ve sahneyi şu şekilde işler: `rt` dokuyu işle.

## Adım 5: Eşdikdörtgen Projeksiyon için Son İşlemi Uygulayın

Bu noktada, küp haritasını eşkenar dörtgen panoramik bir görünüme dönüştürmek için son işlem uygulamamız gerekiyor. Bu dönüşüm, nihai görüntünün düzgün bir panorama olmasını sağlar.

```csharp
PostProcessing equirectangular = renderer.GetPostProcessing("equirectangular");
equirectangular.Input = rt.Targets[0];
renderer.Execute(equirectangular, final);
```

- Eşkenar Dörtgen Projeksiyon: Bu son işlem efekti küp haritasını alır ve onu eşkenar dörtgen panoramik projeksiyona dönüştürerek kusursuz 360 derecelik bir görünüm sağlar.

## Adım 6: İşlenen Panoramayı Kaydedin

İşleme ve son işlem tamamlandıktan sonra, son adım nihai panoramayı PNG gibi bir görüntü dosyasına kaydetmektir.

```csharp
((ITexture2D)final.Targets[0]).Save("Your_Output_Directory/panorama.png", ImageFormat.Png);
```

Bu, panoramik görüntüyü belirtilen dizine kaydeder ve bunu uygulamanıza entegre etmenize veya bir web sitesinde görüntülemenize olanak tanır.

## Çözüm

Aspose.3D for .NET ile 3B sahnelerin panoramik görünümlerini oluşturmak hiç bu kadar kolay olmamıştı. Yukarıda belirtilen adımları izleyerek bir 3B sahneyi kolayca yükleyebilir, kamera ve ışıkları yapılandırabilir, sahneyi işleyebilir ve etkileyici panoramik görüntüler oluşturmak için son işlem efektleri uygulayabilirsiniz. Aspose.3D for .NET, 3B görselleştirmelerinizi hayata geçirmeniz ve bunları uygulamalarınıza sorunsuz bir şekilde entegre etmeniz için gereken gücü ve esnekliği sağlar.

## SSS

### Panoramaları oluşturmak için kendi 3D sahnemi kullanabilir miyim?
Kesinlikle. Örnek sahne dosya yolunu, özel 3B sahnenizin konumuyla değiştirmeniz yeterli.

### Herhangi bir ek son işlem efekti mevcut mu?
Evet, Aspose.3D, işlenmiş görüntülerinizi geliştirmek için uygulanabilen alan derinliği, parlaklık ve daha fazlası gibi bir dizi son işlem efekti sunar.

### Render performansını nasıl optimize edebilirim?
Render performansı, render doku boyutu ve çözünürlük gibi parametrelerin ayarlanması ve kameranın yakın ve uzak düzlemlerinin ayarlanmasıyla optimize edilebilir.

### Bunu bir web uygulamasına entegre edebilir miyim?
Evet, Aspose.3D for .NET, 3D panoramaları dinamik olarak oluşturmak için .NET web uygulamalarınıza entegre edilebilir.

### Aspose.3D desteği için bir topluluk forumu var mı?
Evet, ziyaret edebilirsiniz [Aspose.3D forumu](https://forum.aspose.com/c/3d/18) destek ve topluluk tartışmaları için.