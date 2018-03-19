---
title: "Birim testi ile birim testleri Oluştur komutu yöntemi saplamalar oluşturma | Microsoft Docs"
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- IntelliTest, Get started
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e68235aef04328c637ca12d9dd77cf6176d27669
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-with-microsoft-intellitest"></a>Microsoft IntelliTest ile çalışmaya başlama

* Bu, ilk kez Intellitest ise:
  * Gözcü [Channel 9 video](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Intellitest)
  * Bu okuma [MSDN dergisi bir genel bakış](https://msdn.microsoft.com/magazine/dn904672.aspx)
  * Okuma bizim [belgeleri](../../test/generate-unit-tests-for-your-code-with-intellitest.md)
* Sorular [yığın taşması](http://stackoverflow.com/questions/tagged/intellitest)
* Bu başvuru el ile geri kalanı okuma
* Hızlı başvuru için bu sayfayı yazdırmanız

## <a name="important-attributes"></a>Önemli öznitelikleri

* [PexClass](attribute-glossary.md#pexclass) işaretler türünü içeren **yerleştirin**
* [PexMethod](attribute-glossary.md#pexmethod) işaretleri bir **YERLEŞTİRME**
* [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull) bir null olmayan parametre işaretler

```csharp
using Microsoft.Pex.Framework;

[..., PexClass(typeof(Foo))]
public partial class FooTest {
    [PexMethod]
    public void Bar([PexAssumeNotNull]Foo target, int i) {
        target.Bar(i);
    }
}
```

* [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest) test projesinin bir projesine bağlar
* [PexInstrumentAssembly](attribute-glossary.md#pexinstrumentassemblyattribute) gereç bir derlemeye belirtir

```csharp
[assembly: PexAssemblyUnderTest("MyAssembly")] // also instruments "MyAssembly"
[assembly: PexInstrumentAssembly("Lib")]
```

## <a name="helper-classes"></a> Önemli statik yardımcı sınıfları

* [PexAssume](static-helper-classes.md#pexassume) (giriş filtreleme) varsayımlar değerlendirir
* [PexAssert](static-helper-classes.md#pexassert) onaylar değerlendirir
* [PexChoose](static-helper-classes.md#pexchoose) yeni seçenekleri (ek girdileri) oluşturur
* [PexObserve](static-helper-classes.md#pexobserve) dinamik değerler için oluşturulan testleri günlüğe kaydeder

```csharp
[PexMethod]
void StaticHelpers(Foo target) {
    PexAssume.IsNotNull(target);

    int i = PexChoose.Value<int>("i");
    string result = target.Bar(i);

    PexObserve.ValueForViewing<string>("result", result);
    PexAssert.IsNotNull(result);
}
```

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest).
