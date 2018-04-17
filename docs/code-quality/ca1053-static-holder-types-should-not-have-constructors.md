---
title: 'CA1053: Statik tutucu türlerinde oluşturucular bulunmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0a17b60cd88170a1df2ace72b8a4ee5206fe6d1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: Statik tutucu türlerinde oluşturucular bulunmamalıdır
|||  
|-|-|  
|TypeName|StaticHolderTypesShouldNotHaveConstructors|  
|CheckId|CA1053|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Ortak veya iç içe geçmiş ortak tür yalnızca statik üyeleri bildirir ve ortak veya korumalı varsayılan bir oluşturucu vardır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Statik üyeleri çağırma bir tür örneği gerektirmediğinden kurucu gereksizdir. Statik olmayan üye türü sahip olmadığından, ayrıca, bir örneği oluşturma erişim herhangi bir tür üyeleri için sağlamaz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için varsayılan oluşturucu kaldırın veya özel yap.  
  
> [!NOTE]
>  Tür herhangi oluşturucular tanımlamıyorsa bazı derleyicileri ortak varsayılan bir oluşturucu otomatik olarak oluşturun. Türünüz Durum buysa, ihlalin ortadan kaldırmak için özel varsayılan bir oluşturucu ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Oluşturucusu varlığını türü statik bir tür değil önerir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir. Kaynak kodundaki varsayılan oluşturucu yok olduğuna dikkat edin. Bu kod bir derlemeye derlendiğinde C# Derleyici bu kural ihlal varsayılan bir oluşturucu ekleyin. Bu sorunu gidermek için özel Oluşturucu bildirin.  
  
 [!code-csharp[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]