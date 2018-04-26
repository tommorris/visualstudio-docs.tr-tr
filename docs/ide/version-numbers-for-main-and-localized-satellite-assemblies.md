---
title: Ana ve Yerelleştirilmiş Yardımcı Derlemeler İçin Sürüm Numaraları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- satellite assemblies, version numbers
- SatelliteContractVersionAttribute
- version numbers, assemblies
- assemblies [Visual Studio], version numbers
- versioning, assemblies
ms.assetid: 5489aea1-57b4-4561-9bb4-24d490269602
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4544a1d29cede7922f88c3a1aa7ae053b0b723cb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="version-numbers-for-main-and-localized-satellite-assemblies"></a>Ana ve Yerelleştirilmiş Yardımcı Derlemeler İçin Sürüm Numaraları
<xref:System.Resources.SatelliteContractVersionAttribute> Sınıfı yerelleştirilmiş kaynakları yoluyla Kaynak Yöneticisi'ni kullanan bir ana derleme sürümü oluşturma desteği sağlar. Uygulama <xref:System.Resources.SatelliteContractVersionAttribute> bir uygulamanın ana derleme güncelleştirin ve kendisine ait uydu derlemelerini güncelleştirmeden derleme dağıtmanız olanak tanır. Örneğin, kullanabileceğiniz <xref:System.Resources.SatelliteContractVersionAttribute> yeni kaynaklar yeniden oluşturma ve uydu derlemenizi tanıtmak olmayan bir hizmet paketi sınıfı. Kullanılabilir olması, yerelleştirilmiş kaynaklar için ana derlemenizi uydu sözleşme sürümü eşleşmelidir <xref:System.Reflection.AssemblyVersionAttribute> uydu derlemelerini sınıfı. Bir tam sürüm numarası belirtin <xref:System.Resources.SatelliteContractVersionAttribute>; joker karakterlere gibi "*" izin verilmez. Daha fazla bilgi için bkz: [alma kaynakları](/dotnet/framework/resources/retrieving-resources-in-desktop-apps).

## <a name="updating-assemblies"></a>Derlemeleri güncelleştirme
 <xref:System.Resources.SatelliteContractVersionAttribute> Sınıfı, uydu derlemenizi güncelleştirmek zorunda kalmadan ana derleme güncelleştirmenize olanak verir (veya tersi). Ana derleme güncelleştirildiğinde, derleme sürüm numarası değiştirilir. Varolan uydu derlemelerini kullanmaya devam etmek istiyorsanız, ana derlemenin sürüm numarasını değiştirmek ancak uydu sözleşmesi sürüm numarasını olduğu gibi bırakın. Örneğin, ilk sürümünde, ana derleme sürüm 1.0.0.0 olabilir. Aynı zamanda uydu sözleşme sürüm ve uydu derlemenin derleme sürüm 1.0.0.0 olacaktır. Bir hizmet paketi için ana derlemenizi güncellemeniz gerekiyorsa, uydu sözleşme sürümünün ve uydu derleme sürüm 1.0.0.0 olarak tutarken derleme sürümünü 1.0.0.1 için değiştirebilirsiniz.

 Uydu derlemesi ancak ana derlemenizi güncellemeniz gerekiyorsa, değiştirdiğiniz <xref:System.Reflection.AssemblyVersionAttribute> uydu derlemesinin. Uydu derlemenizi yanı sıra, yeni bir uydu derleme eski uydu derlemenizi ile uyumlu olduğunu belirten bir ilke derlemesi sevk gerekecektir. İlkeler hakkında daha fazla bilgi için bkz: [nasıl çalışma zamanı bulur derlemeleri](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

 Aşağıdaki kod uydu sözleşme sürümünün nasıl ayarlanacağını gösterir. Kod derleme kod veya AssemblyInfo.vb ya da AssemblyInfo.cs dosyasında yerleştirilebilir.

```vb
<Assembly: SatelliteContractVersionAttribute("4.3.2.1")>

```

```csharp
[assembly: SatelliteContractVersionAttribute("4.3.2.1")]
```

## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanının Bütünleştirilmiş Kodların Konumunu Bulması](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [Bütünleştirilmiş Kod Özniteliklerini Ayarlama](/dotnet/framework/app-domains/set-assembly-attributes)
- [Güvenlik ve Yerelleştirilmiş Yardımcı Derlemeler](../ide/security-and-localized-satellite-assemblies.md)
- [Uygulamaları Yerelleştirme](../ide/localizing-applications.md)
- [Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)