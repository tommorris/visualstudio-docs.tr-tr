---
title: 'CA1810: Başvuru türü statik alanları satır içi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e49e346594a8546c6808e718ee7b4d7c78c10b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810: Başvuru türü statik alanları satır içi başlatın
|||  
|-|-|  
|TypeName|InitializeReferenceTypeStaticFieldsInline|  
|CheckId|CA1810|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir başvuru türü açık bir statik Oluşturucu bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir tür açık statik yapıcı bildirdiğinde, JIT derleyici her bir statik yöntemi kontrol ekler ve türün yapıcı örneği statik yapıcının daha önceden çağrıldığından emin olur. Statik başlatma herhangi bir statik üyesi erişildiğinde veya türünün bir örneği oluşturulduğunda tetiklenir. Ancak, türünde bir değişken bildirme, ancak bunu olabilen başlatma genel durumu değişirse önemli kullanmayın statik başlatma tetiklenmez.  
  
 Tüm statik verilerinin başlatılmış satır içi ve açık bir statik Oluşturucu bildirilmemiş Microsoft Ara dili (MSIL) derleyicileri Ekle `beforefieldinit` bayrağı ve hangi MSIL türü statik verileri başlatır bir örtük statik Oluşturucusu tanımı. JIT Derleyici karşılaştığında `beforefieldinit` , çoğu statik Oluşturucusu denetimleri eklenmez zaman bayrak. Statik olarak başlatılması biraz zaman statik alanları erişilen önce ancak statik yöntemi veya örnek oluşturucu başvurulmaz önce gerçekleşmesi için sağlanır. Bu statik başlatma türünde bir değişken bildirildikten sonra herhangi bir zamanda meydana gelebilir unutmayın.  
  
 Statik oluşturucu denetimleri performansı düşürebilir. Çoğunlukla statik Oluşturucu, yalnızca durum, yalnızca statik başlatmanın emin olmalısınız statik bir alana ilk erişim önce oluştuğu statik alanları başlatmak için kullanılır. `beforefieldinit` Davranıştır bu ve diğer birçok türleri için uygun. Yalnızca statik başlatma genel durum etkiler ve aşağıdakilerden biri doğru olduğunda uygunsuz olur:  
  
-   Genel durum etkisi pahalıdır ve türü kullanılmıyorsa, gerekli değildir.  
  
-   Genel durum etkileri herhangi türü statik alanları erişmeden erişilebilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için bildirildiğinde, tüm statik veriyi başlatın ve statik oluşturucuyu kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans ilgili bir sorun değilse bir uyarı bu kuraldan gizlemek güvenlidir; türü için bir statik yöntem çağrılır veya türünün bir örneği oluşturulur önce gerçekleşmesi için tarafından statik olarak başlatılması nedeni genel durum değişiklikleri pahalıdır veya gerekir veya garanti.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `StaticConstructor`, kural ve bir tür ihlal `NoStaticConstructor`, kural karşılamak için satır içi başlatma ile statik Oluşturucusu değiştirir.  
  
 [!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/CSharp/ca1810-initialize-reference-type-static-fields-inline_1.cs)]
 [!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/VisualBasic/ca1810-initialize-reference-type-static-fields-inline_1.vb)]  
  
 Eklenmesi Not `beforefieldinit` bayrağı MSIL tanımında `NoStaticConstructor` sınıfı.  
  
 **Ortak .class otomatik ANSI StaticConstructor**  
 **[mscorlib]System.Object genişletir**  
**{**  
**} / / end StaticConstructor sınıfının**  
**.class ortak otomatik ANSI beforefieldinit NoStaticConstructor**  
 **[mscorlib]System.Object genişletir**  
**{**  
**} / / end NoStaticConstructor sınıfının**   
## <a name="related-rules"></a>İlgili kuralları  
 [CA2207: Değer türü statik alanları satır içi başlatın](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)