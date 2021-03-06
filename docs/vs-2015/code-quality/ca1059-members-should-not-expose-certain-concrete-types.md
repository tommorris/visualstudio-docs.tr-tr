---
title: 'CA1059: Üyeler belli somut türleri göstermemelidir | Microsoft Docs'
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
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 073d55a9a5ae6caa573a2c3db282aaa5e5ea4e57
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902748"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Üyeler belli somut türleri göstermemelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1059: üyeler belli somut türleri kullanıma](https://docs.microsoft.com/visualstudio/code-quality/ca1059-members-should-not-expose-certain-concrete-types).

|||
|-|-|
|TypeName|MembersShouldNotExposeCertainConcreteTypes|
|CheckId|CA1059|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Dışarıdan görünen üye parametrelerinden biri üzerinden belli somut türleri kullanıma sunan belirli bir somut tür veya dönüş değeri. Şu anda, bu kural aşağıdaki somut türleri açığa raporları:

-   Türetilmiş bir tür <xref:System.Xml.XmlNode?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 Somut tür tam bir uygulamaya sahiptir ve bu nedenle oluşturulabilecek bir türdür. Üye yaygın kullanımını izin vermek için önerilen arabirimi ile somut türünü değiştirin. Bu arabirimi uygulayan herhangi bir türü kabul etmesini ya da arabirimi uygulayan bir tür beklenirken kullanılması üye sağlar.

 Aşağıdaki tabloda, hedeflenen somut türleri ve bunların önerilen değişiklikleri listeler.

|Somut tür|Değiştirme|
|-------------------|-----------------|
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> Arabirimi kullanarak bir XML veri kaynağının belirli bir uygulamadan üye ayırır.|

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için önerilen arabirimi somut türünü değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Somut tür tarafından sağlanan belirli işlevleri gerekliyse bu kuraldan bir iletiyi bastırmak güvenlidir.

## <a name="related-rules"></a>İlgili kuralları
 [CA1011: Temel türleri parametre olarak geçirmeyi düşünün](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)



