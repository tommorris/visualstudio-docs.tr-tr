---
title: ': Tanımlayıcılar ca1711 yanlış yok | Microsoft Docs'
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
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ee349aac7b0f4c93502e392e060e4b4636ccf21a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691783"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: Tanımlayıcıların sonekleri yanlış olmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1711: tanımlayıcılar yanlış sonek olmamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1711-identifiers-should-not-have-incorrect-suffix).  
  
TypeName | IdentifiersShouldNotHaveIncorrectSuffix |  
| Checkıd | CA1711 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir tanımlayıcı yanlış bir son eke sahip.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kural gereği, yalnızca, belirli temel türleri genişleten veya bazı arabirimleri ya da bu türlerden türetilmiş türleri uygulayan tür adları, belirli ayrılmış soneklerle bitmelidir. Diğer tür adları aşağıdaki ayrılmış sonekleri kullanmamalı.  
  
 Aşağıdaki tabloda, ayrılmış sonekler ve ilişkili oldukları temel türler ve arabirimler listelenmiştir.  
  
|Son eki|Temel tür arabirimi|  
|------------|--------------------------|  
|Öznitelik|<xref:System.Attribute?displayProperty=fullName>|  
|Koleksiyon|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|  
|Sözlük|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|  
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|  
|EventHandler|Bir olay işletici temsilcisi|  
|Özel Durum|<xref:System.Exception?displayProperty=fullName>|  
|İzin|<xref:System.Security.IPermission?displayProperty=fullName>|  
|Sıra|<xref:System.Collections.Queue?displayProperty=fullName>|  
|Yığın|<xref:System.Collections.Stack?displayProperty=fullName>|  
|Akış|<xref:System.IO.Stream?displayProperty=fullName>|  
  
 Ayrıca, aşağıdaki sonekler **değil** kullanılabilir:  
  
-   Temsilci  
  
-   Enum  
  
-   Impl - yerine 'Core' kullanın  
  
-   Onu aynı türün daha eski bir sürümünden ayırmak için Ex veya benzer sonek  
  
 Adlandırma kuralları, ortak dil çalışma zamanını hedefleyen kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığına sahip olan kişi tarafından geliştirilmiştir müşterilerinizin size olan güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Tür adından soneki kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Sonekte uygulama etki alanında açık bir anlama sahip olmadığı sürece bu kuraldan bir uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1710: Tanımlayıcıların sonekleri doğru olmalıdır](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öznitelikleri](http://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)   
 [NIB: Olayları ve temsilciler](http://msdn.microsoft.com/en-us/d98fd58b-fa4f-4598-8378-addf4355a115)


