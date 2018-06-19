---
title: 'CA2120: Serileştirme oluşturucularının güvenliğini sağlayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 449258d04b6a47fef42c56637a4de48a4e5d1d12
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915397"
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: Serileştirme oluşturucularının güvenliğini sağlayın
|||
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Tür uygular <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi, bir temsilci ya da arabirimi değildir ve kısmen güvenilen arayanlara izin veren bir derlemede bildirilir. Alan bir oluşturucu türüne sahip bir <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> nesne ve <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> nesne (seri hale getirme Oluşturucusu imzası). Bu oluşturucu tarafından güvenlik denetimi güvenli değildir, ancak bir veya daha fazla türü normal kurucularda güvenli.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural, özel serileştirme destekleyen türler için geçerlidir. Bunu uygularsa bir tür özel serileştirme destekleyen <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi. Seri hale getirme Oluşturucusu gereklidir ve seri durumundan veya kullanılarak serileştirilmiş nesneler yeniden oluşturmak için kullanılan <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi. Seri hale getirme Oluşturucusu ayırır ve nesneleri başlatır olduğundan, normal oluşturucular üzerinde mevcut olan güvenlik denetimleri de seri hale getirme Oluşturucu mevcut olması gerekir. Bu kural ihlal varsa, yalnızca bir örneği oluşturulamadı, bunu yapmak için seri hale getirme Oluşturucusu kullanabilirsiniz.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için diğer oluşturucular koruma olanlar aynı güvenlik taleplerini serileştirme Oluşturucusu koruyun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Kural ihlal engelleme.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.

 [!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>