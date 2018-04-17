---
title: 'CA2112: Güvenli türler alanları açığa çıkarmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 050aa2a5048ed4d58e6b5a285f584eda330f178f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [CA1051: Görünür örnek alanlarını bildirmeyin](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)   
 [Veri ve Modelleme](/dotnet/framework/data/index)