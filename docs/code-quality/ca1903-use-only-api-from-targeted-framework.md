---
title: "CA1903: Yalnızca hedeflenen çerçeveden API kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseOnlyAPIFromTargetedFramework
- CA1903
helpviewer_keywords:
- UseOnlyApiFromTargetedFramework
- CA1903
ms.assetid: efdb5cc7-bbd8-4fa7-9fff-02b91e59350e
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7caff553adfd812e671a2d8643b2352d9868ca43
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1903-use-only-api-from-targeted-framework"></a>CA1903: Yalnızca hedeflenen çerçeveden API kullanın
|||  
|-|-|  
|TypeName|UseOnlyApiFromTargetedFramework|  
|CheckId|CA1903|  
|Kategori|Microsoft.Portability|  
|Yeni Değişiklik|-Bir harici olarak görünür üye veya türün imza karşı harekete zaman kesiliyor.<br /><br /> Bir yöntemin gövdesine harekete zaman olmayan sonu -.|  
  
## <a name="cause"></a>Sebep  
 Bir üye ya da türü bir üye ya da projenin hedef çerçevesi ile eklenmedi bir hizmet paketi sürümünde sunulan türü kullanıyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yeni üyeler ve türleri .NET Framework 2.0 Service Pack 1 ve 2, .NET Framework 3.0 Service Pack 1 ve 2 ve .NET Framework 3.5 Service Pack 1'de eklendi. .NET Framework'ün önemli sürümlerini hedefleyen projeler, yeni API'leri bu bağımlılıkları kasıtsız olarak alabilir. Bu bağımlılığı önlemek için bu kural tüm yeni üyeler ve projenin hedef çerçevesi varsayılan olarak dahil edilmemiş türlerinin kullanımları tetikler.  
  
 **Hedef Framework ve hizmet paketi bağımlılıkları**  
  
|||  
|-|-|  
|Hedef framework olduğunda|Sürümünde sunulan üyelerinin kullanımları üzerinde etkinleşir|  
|.NET Framework 2.0|.NET framework 2,0 SP1, .NET Framework 2.0 SP2|  
|.NET Framework 3.0|.NET framework 2,0 SP1, .NET Framework 2.0 SP2, .NET Framework 3.0 SP1, .NET Framework 3.0 SP2|  
|.NET Framework 3.5|.NET Framework 3.5 SP1 |  
|.NET Framework 4|Yok|  
  
 Bir projenin hedef çerçevesi değiştirmek için bkz: [belirli bir .NET Framework sürümü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Hizmet paketi bağımlılığı kaldırmak için tüm kullanımları yeni üye veya türü kaldırın. Bu kasıtlı bağımlılık ise, gizlemek veya bu kuralı kapatın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Belirtilen hizmet paketi bilinçli bir bağımlılığı değilse bir uyarı bu kuraldan bastırmak değil. Bu durumda, bu hizmet paketi yüklü olmayan sistemlerde çalıştırmak, uygulamanızın başarısız olabilir. Gizlemek veya bu kasıtlı bağımlılık ise bu kural kapatın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yalnızca .NET 2.0 Service Pack 1'de kullanılabilir DateTimeOffset türü kullanan bir sınıfı gösterir. Bu örnek, .NET Framework 2.0 proje özelliklerini hedef Framework aşağı açılan listesinde seçili gerektirir.  
  
 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yukarıda açıklanan ihlali kullanımları DateTimeOffset türü DateTime türü ile değiştirerek giderir.  
  
 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework2#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_2.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşınabilirlik uyarıları](../code-quality/portability-warnings.md)   
 [Belirli bir .NET Framework sürümünü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md)