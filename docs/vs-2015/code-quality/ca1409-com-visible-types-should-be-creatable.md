---
title: 'CA1409: Com görünebilir türler oluşturulabilmelidir | Microsoft Docs'
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
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 06f4b5c2432e6aba39408a39afdf9870b5479fbb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683743"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Com görünebilir türler oluşturulabilmelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1409: Com görünebilir türler oluşturulabilir](https://docs.microsoft.com/visualstudio/code-quality/ca1409-com-visible-types-should-be-creatable).  
  
TypeName | ComVisibleTypesShouldBeCreatable |  
| Checkıd | CA1409 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Özel Bileşen Nesne Modeli (COM) görünür olarak işaretlenmiş bir başvuru türü, parametreli ortak kurucu içeriyorsa ancak genel varsayılan (parametresiz) bir oluşturucu içermiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Genel bir varsayılan oluşturucu olmadan tür COM istemcileri tarafından oluşturulamıyor. Ancak, başka bir yöntem türü oluşturup istemciye (örneğin, üzerinden bir yöntem çağrısının dönüş değerini) geçirmek kullanılabilir durumdaysa türü hala COM istemcileri tarafından erişilebilir.  
  
 Öğesinden türetilen türler kural yoksayar <xref:System.Delegate?displayProperty=fullName>.  
  
 Varsayılan olarak, COM görünür şunlardır: derlemeleri, genel tür, genel türlerde ortak örnek üyeleri ve tüm ortak türlerin üyeleri.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için ortak varsayılan oluşturucusu ekleme veya kaldırma <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> yazın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yollar oluşturma ve nesneyi COM istemcisi geçirin sağlandıysa bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birlikte çalışma için .NET türlerini niteleme](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)   
 [Yönetilmeyen Kod ile Birlikte Çalışma](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



