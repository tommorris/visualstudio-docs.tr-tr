---
title: 'CA1809: aşırı yerel öğelerden Kaçın | Microsoft Docs'
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
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e5dbd1ffc9a427994d923fda695a8dab0c37dda0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692709"
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809: Aşırı yerel öğelerden kaçın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1809: aşırı yerel öğelerden Kaçın](https://docs.microsoft.com/visualstudio/code-quality/ca1809-avoid-excessive-locals).  
  
TypeName | AvoidExcessiveLocals |  
| Checkıd | CA1809 |  
| Kategori | Microsoft.Performance|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Üye bazıları derleyici tarafından oluşturulmuş olabilir, 64'ten fazla yerel değişkenler içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Olarak adlandırılan bellek yerine işlemci kayıttaki değeri depolamak için yaygın bir performans iyileştirmesidir olduğu *kayıt* değeri. Ortak dil çalışma zamanı enregistration için en fazla 64 yerel değişkenler olarak değerlendirir. Kaydedilme olmayan değişkenler yığına yerleştirilir ve işleme önce bir kayıt taşınması gerekir. Fırsat izin vermek için tüm yerel değişkenlerin kaydedilme alın, 64 yerel değişken sayısını sınırlayın.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için en fazla 64 yerel değişken kullanmak için uygulama yeniden düzenleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans sorunu değilse bu kuraldan bir uyarıyı bastırmak için veya kuralı devre dışı bırakmak için güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)



