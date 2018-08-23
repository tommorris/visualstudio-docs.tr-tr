---
title: 'CA2228: yayımlanmamış kaynak biçimlerini yollamayın | Microsoft Docs'
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
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 324803c5a840d1ef728d47845e548acc886348ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695700"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Yayımlanmamış kaynak biçimlerini yollamayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2228: yayımlanmamış kaynak biçimlerini yollamayın](https://docs.microsoft.com/visualstudio/code-quality/ca2228-do-not-ship-unreleased-resource-formats).  
  
TypeName | DoNotShipUnreleasedResourceFormats |  
| Checkıd | CA2228 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir kaynak dosyası bir sürümü kullanılarak oluşturulmuş [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] , şu anda desteklenmiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yayın öncesi sürümlerini kullanarak oluşturulan kaynak dosyaları [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] desteklenen .NET Framework sürümleri tarafından kullanılamayabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için desteklenen bir sürümünü kullanarak kaynak oluşturma [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]k.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.



