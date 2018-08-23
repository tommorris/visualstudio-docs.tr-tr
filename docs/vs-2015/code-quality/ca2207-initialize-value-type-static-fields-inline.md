---
title: 'CA2207: Değer türü statik alanları satır içi başlatın | Microsoft Docs'
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
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1329cb10e417a337f6b8f10f8df92e0a13f8ea7f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696053"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Değer türü statik alanları satır içi başlatın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2207: değer türü statik alanları satır içi başlatın](https://docs.microsoft.com/visualstudio/code-quality/ca2207-initialize-value-type-static-fields-inline).  
  
TypeName | InitializeValueTypeStaticFieldsInline |  
| Checkıd | CA2207 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir değer türü açık bir statik Oluşturucu bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir değer türü bildirildiğinde, burada tüm değer tür alanları sıfıra ayarlanır ve tüm başvuru türü alanlarını ayarlamak bir varsayılan başlatma uğradığında `null` (`Nothing` Visual Basic'te). Açık bir statik Oluşturucu yalnızca bir örnek oluşturucusu önce çalıştırması garantili olan veya türün statik üyesi çağrılır. Türün örnek oluşturucusu çağırmaya gerek kalmadan oluşturulursa, bu nedenle, statik Oluşturucusu çalıştırmak için garanti edilmez.  
  
 Tüm statik verileri başlatılmış satır içi olduğundan ve hiçbir açık bir statik Oluşturucu bildirimi, C# ve Visual Basic derleyicileri ekleyin `beforefieldinit` MSIL sınıf tanımına bayrağı. Derleyiciler, ayrıca statik başlatma kodu içeren özel bir statik oluşturucu ekleyin. Bu özel bir statik Oluşturucu tüm türü statik alanları erişebilmek için önce çalıştırılacak garanti edilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Düzeltmek için bu kural ihlalini başlatmak tüm statik verileri bildirilir ve statik oluşturucuyu kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1810: Başvuru türü statik alanları satır içi başlatın](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)



