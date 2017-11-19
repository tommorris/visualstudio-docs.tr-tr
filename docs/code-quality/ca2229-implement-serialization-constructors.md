---
title: "CA2229: Serileştirme oluşturucularını uygulayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5d262718e6728a87cb955019fff0ce95db2b49d2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: Serileştirme oluşturucularını uygulayın
|||  
|-|-|  
|TypeName|ImplementSerializationConstructors|  
|CheckId|CA2229|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Tür uygular <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi, bir temsilci veya arabirim değil ve aşağıdaki koşullardan biri doğru:  
  
-   Türün alan bir oluşturucu yok bir <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> nesne ve <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> nesne (seri hale getirme Oluşturucusu imzası).  
  
-   Türü korumasız ve seri hale getirme kurucusu erişim değiştiricisi korumalı (ailesi) değil.  
  
-   Türü korumalı ve seri hale getirme kurucusu erişim değiştiricisi özel değildir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, özel serileştirme destekleyen türler için geçerlidir. Bunu uygularsa bir tür özel serileştirme destekleyen <xref:System.Runtime.Serialization.ISerializable> arabirimi. Seri hale getirme Oluşturucusu seri durumdan veya kullanılarak serileştirilmiş nesneler yeniden oluşturmak için gereken <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için seri hale getirme yapıcısını uygular. Kapalı bir sınıf için kurucusunu özel yapın; aksi takdirde korunmuş yapın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kural ihlal engelleme. Türü serisi olmaz ve birçok senaryoda çalışmaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kural karşılayan bir türünü gösterir.  
  
 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>