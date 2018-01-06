---
title: "CA1700: numaralandırma değerleri &#39;ad değil; Ayrılmış &#39; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1700
- DoNotNameEnumValuesReserved
helpviewer_keywords:
- DoNotNameEnumValuesReserved
- CA1700
ms.assetid: 7a7e01c3-ae7d-4c82-a646-91b58864a749
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e97c2da18531584128c48c9aac36ebb16ae86cc4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1700-do-not-name-enum-values-39reserved39"></a>CA1700: numaralandırma değerleri &#39;ad değil; Ayrılmış &#39;
|||  
|-|-|  
|TypeName|DoNotNameEnumValuesReserved|  
|CheckId|CA1700|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir numaralandırma üyesine adını "ayrılmış" sözcüğünü içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, "ayrılmış" içeren bir ada sahip numaralandırma üyesi şu anda kullanılmamaktadır ancak yeniden adlandırılabilir veya gelecekteki bir sürüme kaldırıldığını varsayar. Üye kaldırma veya yeniden adlandırma bölünmesi farklıdır. Kullanıcılar yalnızca kendi adı "ayrılmış" içeriyor ya da okuma veya belge tarafından uymanız kullanıcıları güvenebilirsiniz çünkü bir üyeyi göz ardı beklememeniz gerekir. Ayrıca, nesne tarayıcılar ve akıllı tümleşik geliştirme ortamlarını ayrılmış üyeler görünür olduğundan, bunlar hakkında üyeleri gerçekte kullanılmakta olan karışıklığa neden olabilir.  
  
 Ayrılmış üyesi kullanmak yerine, gelecek sürümünde numaralandırma için yeni bir üye ekleyin. Ayrıca değiştirmek için özgün üyelerinin değerlerini neden olmaz sürece çoğu durumda yeni üye eklenmesi önemli bir değişiklik değil.  
  
 Bile özgün değerlerine özgün üyeler tutmak zaman durumlarda sınırlı bir süre içinde bir üyenin önemli bir değişiklik ektir. Öncelikle, yeni üye var olan kod yolları kullanın arayanlar bozmadan iade edilemez bir `switch` (`Select` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) deyimi tüm üye listesini kapsar ve bu durum bir özel durum dönüş değeri varsayılan durumu. Bir ikincil istemci kodu yansıma yöntemlerden davranışında değişiklik gibi işleme değil konudur <xref:System.Enum.IsDefined%2A?displayProperty=fullName>. Buna uygun olarak, yeni üye mevcut yöntemler arasından döndürülecek veya bilinen uygulama uyumsuzluğu nedeniyle zayıf yansıma kullanımı oluşuyor varsa yalnızca bölünemez için çözümüdür:  
  
1.  Özgün ve yeni üyeleri içeren yeni bir numaralandırma ekleyin.  
  
2.  Özgün numaralandırması ile işaretle <xref:System.ObsoleteAttribute?displayProperty=fullName> özniteliği.  
  
 Herhangi bir harici olarak görünebilir türler veya özgün numaralandırması kullanıma üyeleri için aynı yordamı izleyin.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kaldırmak veya üye yeniden adlandırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Şu anda kullanılan bir üye ya da daha önce gönderilen kitaplıkları için bu kural bir uyarıdan gizlemek güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1712: Numaralandırma değerleri için tür adıyla önek kullanmayın](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
 [CA1028: Numaralandırma depolaması Int32 olmalıdır](../code-quality/ca1028-enum-storage-should-be-int32.md)  
  
 [CA1008: Numaralandırmalar sıfır değerine sahip olmalıdır](../code-quality/ca1008-enums-should-have-zero-value.md)  
  
 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)