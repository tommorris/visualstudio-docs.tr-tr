---
title: 'CA1059: Üyeler belli somut türleri göstermemelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04e8348dc77222fbc06887efebf44c735eb7c8f0
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550027"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Üyeler belli somut türleri göstermemelidir
|||
|-|-|
|TypeName|MembersShouldNotExposeCertainConcreteTypes|
|CheckId|CA1059|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Dışarıdan görünen üye parametrelerinden biri üzerinden belli somut türleri kullanıma sunan belirli bir somut tür veya dönüş değeri. Şu anda, bu kural aşağıdaki somut türleri açığa raporları:

- Türetilmiş bir tür <xref:System.Xml.XmlNode?displayProperty=fullName>.

## <a name="rule-description"></a>Kural açıklaması
 Somut tür tam bir uygulamaya sahiptir ve bu nedenle oluşturulabilecek bir türdür. Üye yaygın kullanımını izin vermek için önerilen arabirimi ile somut türünü değiştirin. Bu arabirimi uygulayan herhangi bir türü kabul etmesini ya da arabirimi uygulayan bir tür beklenirken kullanılması üye sağlar.

 Aşağıdaki tabloda, hedeflenen somut türleri ve bunların önerilen değişiklikleri listeler.

|Somut tür|Değiştirme|
|-------------------|-----------------|
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> Arabirimi kullanarak bir XML veri kaynağının belirli bir uygulamadan üye ayırır.|

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için önerilen arabirimi somut türünü değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Somut tür tarafından sağlanan belirli işlevleri gerekliyse bu kuraldan bir iletiyi bastırmak güvenlidir.

## <a name="related-rules"></a>İlgili kuralları
 [CA1011: Temel türleri parametre olarak geçirmeyi düşünün](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)