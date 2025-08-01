---
"description": "Naučte se, jak vykreslit úžasný panoramatický pohled na 3D scénu ve vašich .NET aplikacích pomocí Aspose.3D. Postupujte podle našeho podrobného návodu pro imerzivní vykreslování scén."
"linktitle": "Vykreslení panoramatického pohledu 3D scény"
"second_title": "Rozhraní Aspose.3D .NET API"
"title": "Vykreslení panoramatického pohledu 3D scény pomocí Aspose.3D pro .NET"
"url": "/cs/3d/net/guide-to-rendering/render-panorama-view-3d-scene/"
"weight": 13
---

## Zavedení

Vytváření pohlcujících panoramatických 3D scén je pro vývojáře, kteří chtějí vylepšit své aplikace ohromujícími vizuálními efekty, převratným krokem. Ať už pracujete na herním enginu, architektonické vizualizaci nebo pohlcujících webových zážitcích, vykreslování 3D scén jako panoramat umožňuje uživatelům zažít dynamický pohled ze všech úhlů. Aspose.3D pro .NET je perfektní nástroj pro bezproblémovou integraci této funkce do vašich .NET projektů. Tato komplexní příručka vás provede procesem vykreslování panoramatu z 3D scény pomocí Aspose.3D pro .NET.

## Předpoklady

Než se pustíte do procesu renderování, ujistěte se, že máte připraveno následující:

- Aspose.3D pro .NET: Nejprve je třeba nainstalovat Aspose.3D, který poskytuje všechny potřebné nástroje pro práci s 3D prvky a renderování. [Stáhněte si Aspose.3D pro .NET](https://releases.aspose.com/3d/net/) začít.
- Vývojové prostředí .NET: Je vyžadováno plně nakonfigurované vývojové prostředí .NET. Ujistěte se, že máte Visual Studio nebo jiné kompatibilní vývojové prostředí (IDE).
- Ukázkový soubor 3D scény: Můžete použít libovolnou 3D scénu ve formátech, jako například `.glb`, `.fbx`, nebo `.obj`V tomto tutoriálu použijeme jednoduchý soubor „VirtualCity.glb“.

Jakmile splníte tyto předpoklady, můžeme přejít k nastavení scény.

## Importovat nezbytné jmenné prostory

Pro práci s Aspose.3D budeme muset do našeho projektu importovat několik jmenných prostorů. Tyto jmenné prostory nám umožňují efektivně manipulovat s 3D objekty, nastavením kamery a možnostmi vykreslování.

```csharp
using Aspose.ThreeD;
using Aspose.ThreeD.Entities;
using Aspose.ThreeD.Render;
using Aspose.ThreeD.Utilities;
using System;
using System.Drawing;
using System.Drawing.Imaging;
```

Tyto jmenné prostory jsou nezbytné pro načtení 3D scény, konfiguraci kamery, osvětlení a nastavení renderovaných textur, které tvoří panoramatický pohled.

## Krok 1: Načtěte 3D scénu do aplikace

Prvním krokem je načtení 3D scény do vaší aplikace. Toho lze dosáhnout pomocí `Scene` třída poskytovaná Aspose.3D. Nahradit `"VirtualCity.glb"` s cestou k souboru 3D scény.

```csharp
Scene scene = new Scene("path_to_your_scene/VirtualCity.glb");
```

Ten/Ta/To `Scene` Objekt načte 3D scénu do paměti, což vám umožní s ní interagovat a aplikovat techniky vykreslování.

## Krok 2: Nastavení kamery a světel

Abyste zajistili správné zachycení 3D scény, budete muset nastavit kameru a vhodné osvětlení. Kamera umožňuje ovládat perspektivu scény, zatímco světla pomáhají osvětlovat objekty.

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

- Nastavení kamery: Blízká a vzdálená rovina kamery jsou nastaveny tak, aby definovaly viditelný rozsah ve 3D scéně.
- Nastavení světla: Jsou přidána dvě světla – jedno bodové a druhé se specifickou barvou, které dodává scéně hloubku a realismus.

## Krok 3: Nastavení rendereru a definování cílů renderování

Nyní, když máte scénu, kameru a světla nastavená, je dalším krokem vytvoření rendereru a definování cílů renderu. Renderer je zodpovědný za generování 3D obrázků a cíle renderu definují, kam bude uložen finální výstup.

```csharp
using (var renderer = Renderer.CreateRenderer())
{
    IRenderTexture rt = renderer.RenderFactory.CreateCubeRenderTexture(new RenderParameters(false), 512, 512);
    IRenderTexture final = renderer.RenderFactory.CreateRenderTexture(new RenderParameters(false, 32, 0, 0), 1024 * 3, 1024);
}
```

- Textura pro vykreslení krychle: Používá se k vykreslení krychlové mapy pro panoramatický pohled. Zde definujeme texturu o rozměrech 512x512.
- Finální textura renderu: Toto je textura, která bude obsahovat finální ekvidistantní panoramatický pohled.

## Krok 4: Konfigurace výřezu a vykreslení scény

Po vytvoření textur pro renderování musíme nakonfigurovat výřez, který definuje oblast 3D scény, kterou bude kamera zachytit.

```csharp
rt.CreateViewport(cam, RelativeRectangle.FromScale(0, 0, 1, 1));
renderer.Render(rt);
```

Tento kód nastaví zobrazovací oblast pro mapu krychle a vykreslí scénu do `rt` vykreslení textury.

## Krok 5: Použití postprocessingu pro ekvidistantní projekci

V tomto bodě musíme provést následné zpracování, abychom převedli krychlovou mapu do ekvidistantního panoramatického pohledu. Tato transformace zajistí, že výsledný obrázek bude správným panoramatem.

```csharp
PostProcessing equirectangular = renderer.GetPostProcessing("equirectangular");
equirectangular.Input = rt.Targets[0];
renderer.Execute(equirectangular, final);
```

- Ekvirektangulární projekce: Tento efekt následného zpracování transformuje krychlovou mapu do ekviditangulární panoramatické projekce, která poskytuje plynulý 360stupňový pohled.

## Krok 6: Uložení vykresleného panoramatu

Jakmile je vykreslení a následné zpracování dokončeno, posledním krokem je uložení finálního panoramatu do obrazového souboru, například PNG.

```csharp
((ITexture2D)final.Targets[0]).Save("Your_Output_Directory/panorama.png", ImageFormat.Png);
```

Tím se panoramatický snímek uloží do zadaného adresáře, což vám umožní jej integrovat do vaší aplikace nebo zobrazit na webových stránkách.

## Závěr

Vykreslování panoramatických pohledů 3D scén nebylo s Aspose.3D pro .NET nikdy snazší. Dodržováním výše uvedených kroků můžete snadno načíst 3D scénu, nakonfigurovat kameru a světla, vykreslit scénu a aplikovat efekty následného zpracování pro generování pohlcujících panoramatických snímků. Aspose.3D pro .NET poskytuje výkon a flexibilitu, která vdechne vašim 3D vizualizacím život a bezproblémově je integruje do vašich aplikací.

## Často kladené otázky

### Mohu pro vykreslování panoramat použít vlastní 3D scénu?
Rozhodně. Jednoduše nahraďte cestu k souboru vzorové scény umístěním vaší vlastní 3D scény.

### Jsou k dispozici nějaké další efekty pro následné zpracování?
Ano, Aspose.3D nabízí řadu efektů pro následné zpracování, jako je hloubka ostrosti, rozkvět a další, které lze použít k vylepšení vykreslených obrázků.

### Jak mohu optimalizovat výkon vykreslování?
Výkon renderování lze optimalizovat úpravou parametrů, jako je velikost a rozlišení renderované textury, a také úpravou blízkých a vzdálených rovin kamery.

### Mohu tohle integrovat do webové aplikace?
Ano, Aspose.3D pro .NET lze integrovat do vašich webových aplikací .NET pro dynamické vykreslování 3D panoramat.

### Existuje nějaké komunitní fórum pro podporu Aspose.3D?
Ano, můžete navštívit [Fórum Aspose.3D](https://forum.aspose.com/c/3d/18) pro podporu a diskuze v komunitě.