---
title: "CA2207: Değer türü statik alanları satır içi başlatın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7f22975ba591e4300e54a4bda01f3802b393ae59
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Değer türü statik alanları satır içi başlatın
|||  
|-|-|  
|TypeName|InitializeValueTypeStaticFieldsInline|  
|CheckId|CA2207|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Değer türü açık bir statik Oluşturucu bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Değer türü bildirilmişse, burada tüm değer türü alanları sıfıra ayarlanır ve tüm başvuru türü alanlarını ayarlamak bir varsayılan başlatma uğradığında `null` (`Nothing` Visual Basic'te). Açık bir statik Oluşturucu yalnızca bir örnek oluşturucusu önce çalıştırması garantili olan veya statik üye türü olarak adlandırılır. Örnek oluşturucu çağırmadan türü oluşturduysanız, bu nedenle, statik oluşturucusunu çalıştırmak için kesin değildir.  
  
 Tüm statik verilerin başlatılmış satır içi olduğundan ve hiçbir açık statik Oluşturucu bildirilmiş, C# ve Visual Basic derleyicileri ekleyin `beforefieldinit` MSIL sınıf tanımına bayrağı. Derleyicileri de statik başlatma kodunu içeren özel bir statik oluşturucu ekleyin. Bu özel statik Oluşturucusu herhangi türü statik alanları erişilen önce çalıştırılacak garanti edilmez.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Düzeltmek için bu kural ihlal başlatmak tüm statik verileri bildirilir ve statik Oluşturucusu kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1810: Başvuru türü statik alanları satır içi başlatın](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)