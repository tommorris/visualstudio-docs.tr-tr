---
title: "CA1025: Tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9e6142ff6670edd6eb1f4cad009b68005b27a86f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: Tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin
|||  
|-|-|  
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|  
|CheckId|CA1025|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir genel veya korumalı yöntemi genel türde birden fazla üç parametre vardır ve son üç parametreleri aynı türdeyse.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir parametre dizisi yerine yinelenen bağımsız değişken bağımsız değişken tam sayısı bilinmiyor ve değişken bağımsız değişkenleri aynı türde olan ya da aynı türde geçirilebilir kullanın. Örneğin, <xref:System.Console.WriteLine%2A> yöntemi sağlar herhangi bir sayıda kabul etmek için bir parametre dizisi kullanan bir genel amaçlı aşırı <xref:System.Object> bağımsız değişkenler.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yinelenen bağımsız değişkenler bir parametre dizisi ile değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Her zaman bir uyarı bu kuraldan gizlemek güvenlidir; Ancak, bu tasarım kullanılabilirlik sorunlara neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]