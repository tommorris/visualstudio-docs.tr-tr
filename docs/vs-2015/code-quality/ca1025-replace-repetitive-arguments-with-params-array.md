---
title: 'CA1025: Tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e51f92c46d3d8ac75e6de7b6d5b8b505c8b25503
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688839"
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: Tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1025: tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin](https://docs.microsoft.com/visualstudio/code-quality/ca1025-replace-repetitive-arguments-with-params-array).  
  
TypeName | ReplaceRepetitiveArgumentsWithParamsArray |  
| Checkıd | CA1025 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Ortak türde ortak veya korumalı bir yöntem üçten fazla parametre içeriyor ve son üç parametrelerini aynı türdedir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir parametre dizisi bağımsız değişken bir tam sayısı bilinmiyor ve değişken bağımsız değişkenler aynı türde olan ya da aynı türde geçirilebilir geçirilebileceğinde bağımsız değişkenleri kullanın. Örneğin, <xref:System.Console.WriteLine%2A> yöntemi herhangi bir sayıda kabul etmek için bir parametre dizisi kullanan bir genel amaçlı bir aşırı yüklemesini sağlar <xref:System.Object> bağımsız değişkenler.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için yinelenen bağımsız değişken bir parametre dizisi ile değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan bir uyarıyı bastırmak her zaman güvenlidir; Ancak, bu tasarım, kullanılabilirlik sorunlara neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bu kuralı ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Design.RepeatArgs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RepeatArgs/cs/FxCop.Design.RepeatArgs.cs#1)]



