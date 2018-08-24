---
title: 'CA2229: Serileştirme oluşturucularını uygulayın | Microsoft Docs'
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
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 815e2ad834e806e79391664e0576fad8f8ab9bd0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629972"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: Serileştirme oluşturucularını uygulayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2229: Serileştirme oluşturucularını uygulayın](https://docs.microsoft.com/visualstudio/code-quality/ca2229-implement-serialization-constructors).  
  
TypeName | ImplementSerializationConstructors |  
| Checkıd | CA2229 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Türün uyguladığı <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirim, temsilci veya arabirimi değil ve aşağıdaki koşullardan biri doğru:  
  
-   Tür, alan bir oluşturucu yok. bir <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> nesnesi ve bir <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> nesnesi (seri hale getirme oluşturucusunu imzası).  
  
-   Korumasız bir türdür ve seri hale getirme oluşturucusuna ait erişim değiştiricisinin (Aile) korumalı değil.  
  
-   Tür Mühürlü olmadığı ve seri hale getirme oluşturucusuna ait erişim değiştiricisinin özel değildir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, özel serileştirme destekleyen türler için geçerlidir. Bunu uygulayan bir tür özel serileştirme destekler <xref:System.Runtime.Serialization.ISerializable> arabirimi. Seri hale getirme oluşturucusunu seri durumdan veya kullanılarak serileştirilmiş nesneler yeniden oluşturmak için gerekli <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için seri hale getirme yapıcısını uygular. Kapalı bir sınıf için kurucusunu özel yapın; aksi takdirde korunmuş yapın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural ihlalini bastırmayın. Türü seri durumdan olmayacaktır ve pek çok senaryoda çalışmaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kural karşılayan bir tür gösterir.  
  
 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ISerializableCtor/cs/FxCop.Usage.ISerializableCtor.cs#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>


