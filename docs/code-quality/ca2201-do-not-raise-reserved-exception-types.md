---
title: "CA2201: ayrılmış özel durum türleri yükseltmeyin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 713018b96aed70d52b1b11e75b0c2993312ef474
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201: Ayrılmış özel durum türleri oluşturmayın
|||  
|-|-|  
|TypeName|DoNotRaiseReservedExceptionTypes|  
|CheckId|CA2201|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir yöntem çok genel veya çalışma zamanı tarafından ayrılmış bir özel durum türü başlatır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kullanıcı için yeterli bilgi sağlamak için genel aşağıdaki özel durum türleri şunlardır:  
  
-   <xref:System.Exception?displayProperty=fullName>  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.SystemException?displayProperty=fullName>  
  
 Aşağıdaki özel durum türleri ayrılmış ve yalnızca ortak dil çalışma zamanı tarafından oluşturulur:  
  
-   <xref:System.ExecutionEngineException?displayProperty=fullName>  
  
-   <xref:System.IndexOutOfRangeException?displayProperty=fullName>  
  
-   <xref:System.NullReferenceException?displayProperty=fullName>  
  
-   <xref:System.OutOfMemoryException?displayProperty=fullName>  
  
 **Genel özel durumlar oluşturma değil**  
  
 Genel özel durum türü gibi throw varsa <xref:System.Exception> veya <xref:System.SystemException> bir kitaplık veya framework tüm yakalamak üzere tüketiciler zorlar nasıl yapılacağını bilmiyorsanız Bilinmeyen özel durumlar dahil olmak üzere özel durumlar.  
  
 Bunun yerine, zaten var çerçevesinde daha türetilmiş bir tür throw ya da türetilen kendi türü oluşturma <xref:System.Exception>.  
  
 **Belirli özel durumlar oluşturma**  
  
 Aşağıdaki tabloda parametreleri gösterir ve bir özelliğin set erişimcisi değer parametresi dahil olmak üzere parametre doğruladığınızda throw için hangi özel durumlar:  
  
|Parametre açıklaması|Özel Durum|  
|---------------------------|---------------|  
|`null`başvuru|<xref:System.ArgumentNullException?displayProperty=fullName>|  
|İzin verilen değerleri (örneğin, bir koleksiyon ya da liste için bir dizin) aralığının dışında|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|  
|Geçersiz `enum` değeri|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|  
|Bir yöntemin parametre belirtimleri karşılamıyor bir biçim içeriyor (için biçim dizesi gibi `ToString(String)`)|<xref:System.FormatException?displayProperty=fullName>|  
|Aksi takdirde geçersiz|<xref:System.ArgumentException?displayProperty=fullName>|  
  
 Bir işlem nesnesi throw geçerli durumu için geçersiz olduğunda<xref:System.InvalidOperationException?displayProperty=fullName>  
  
 Atıldı bir nesne üzerinde bir işlemi gerçekleştirildiğinde throw<xref:System.ObjectDisposedException?displayProperty=fullName>  
  
 Ne zaman bir işlem desteklenmiyor (örn. bir geçersiz kılınan **Stream.Write** okumak için açılan bir akış) throw<xref:System.NotSupportedException?displayProperty=fullName>  
  
 Bir dönüştürme (bir açık atama işleci aşırı olduğu gibi) taşma neden olacağından, throw<xref:System.OverflowException?displayProperty=fullName>  
  
 Tüm diğer durumlarda, türetilen kendi türü oluşturmayı düşünün <xref:System.Exception> ve bu durum.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için ayrılmış türlerinden birini değil belirli bir tür oluşturulan özel durum türünü değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1031: genel özel durum türleri catch değil](../code-quality/ca1031-do-not-catch-general-exception-types.md)