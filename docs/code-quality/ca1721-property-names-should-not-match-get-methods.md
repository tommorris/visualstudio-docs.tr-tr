---
title: "Ca1721: tür Get yöntemleri özellik adları eşleşmemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eb0a1b45276e6563ab645100377dec25a9060e06
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: Tür adları alma metotlarıyla eşleşmemelidir
|||  
|-|-|  
|TypeName|PropertyNamesShouldNotMatchGetMethods|  
|CheckId|CA1721|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Genel veya korumalı bir üyenin adını 'Get' ile başlar ve aksi halde bir genel veya korumalı özellik adıyla eşleşen. Örneğin, 'GetColor' ve 'Color' adlı bir özellik adlı bir yöntem içeren bir türü bu kural ihlal ediyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Get yöntemleri ve özellikleri açıkça işlevlerine ayırt adlar olmalıdır.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu yeni bir yazılım kitaplığı öğrenmek için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır süreyi azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Adı 'Get' ile önekli bir yöntemin adı eşleşmiyor şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
> [!NOTE]
>  Get yöntemini Iextenderprovider arabirimi uygulayarak neden oluyorsa bu uyarı atlanabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yöntemi ve bu kural ihlal özelliği içerir.  
  
 [!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
 [!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)