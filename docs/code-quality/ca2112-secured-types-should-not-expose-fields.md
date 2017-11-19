---
title: "CA2112: Güvenli türler alanları açığa çıkarmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d60784b92d414b6a226605cd406378c1686529dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Güvenli türler alanları açığa çıkarmamalıdır
|||  
|-|-|  
|TypeName|SecuredTypesShouldNotExposeFields|  
|CheckId|CA2112|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir genel ya da korumalı türü genel alanlar içeriyor ve tarafından güvenliği sağlanan bir [bağlantı talepleri](/dotnet/framework/misc/link-demands).  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bağlantı talebi tarafından güvenli türde bir örnek kod erişimi varsa, kod türün alanlarına erişmek için bağlantı talebine sahip değildir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alanları özel yapmak ve ortak özellik veya alan verisi döndüren yöntemler ekleyin. LinkDemand güvenlik denetimlerini türlerinde tür özellikleri ve yöntemleri erişimi koruyun. Bununla birlikte, kod erişim güvenliği alanlar için geçerli değildir.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Güvenlik sorunları hem iyi tasarım, genel alanlar özel yaparak ihlalleri sorununu çözer. Alan güvenli kalması gereken bilgileri barındırmıyorsa bu kural bir uyarıdan gizleyebilirsiniz ve alan içeriğine güvenmeyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir kitaplık türü oluşur (`SecuredTypeWithFields`) güvenli alanlarla bir türü (`Distributor`) kitaplığı türünün örneklerini oluşturabilir ve türleri hatalı geçişleri örneklerine bunları oluşturmak için izne sahip değil ve uygulama kodu türü korur izni yok olsa bile bir örneğinin alanları okuyabilir.  
  
 Aşağıdaki kitaplık kodu kuralını ihlal ediyor.  
  
 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]  
  
## <a name="example"></a>Örnek  
 Uygulamanın bir örneği güvenli türü korur bağlantı isteği nedeniyle oluşturulamıyor. Aşağıdaki sınıf güvenli türünün bir örneği elde etmek uygulama sağlar.  
  
 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama güvenli türünün yöntemleri erişim izni alanlarını kodu nasıl erişebilirsiniz gösterilmektedir.  
  
 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **SecuredTypeWithFields örneği oluşturma.**  
**Tür alanları güvenli: 22, 33**  
**Güvenli tür alanı değiştiriliyor...**  
**Nesne alanları önbelleğe: 99, 33**   
## <a name="related-rules"></a>İlgili kuralları  
 [CA1051: görünür örnek alanlarını bildirme](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)   
 [Veri ve modelleme](/dotnet/framework/data/index)